-----------------------------------------------------------------------
1. Weather Analysis

There is a table with daily weather data over the last 6 months of 2020, including the maximum, minimum, and average temperatures.


Write a query that gives month, monthly maximum, monthly minimum, monthly average temperatures for the six months.

Note: Round the average to the nearest integer.
-----------------------------------------------------------------------

select
	cast(substring_index (substring_index (record_date, '-',-2), '-', 1) as UNSIGNED) as mon1,
	(
	select
		max(tr2.data_value)
	from
		temperature_records tr2
	where
		cast(substring_index (substring_index (tr2.record_date, '-',-2), '-', 1) as UNSIGNED)= mon1
		and data_type = 'max'
	group by
		cast(substring_index (substring_index (tr2.record_date, '-',-2), '-', 1) as UNSIGNED)
),
	(
	select
		min(tr3.data_value)
	from
		temperature_records tr3
	where
		cast(substring_index (substring_index (tr3.record_date, '-',-2), '-', 1) as UNSIGNED)= mon1
			and data_type = 'min'
		group by
			cast(substring_index (substring_index (tr3.record_date, '-',-2), '-', 1) as UNSIGNED)
),
	(
	select
		round(avg(tr4.data_value))
	from
		temperature_records tr4
	where
		cast(substring_index (substring_index (tr4.record_date, '-',-2), '-', 1) as UNSIGNED)= mon1
			and data_type = 'avg'
		group by
			cast(substring_index (substring_index (tr4.record_date, '-',-2), '-', 1) as UNSIGNED)
)
from
	temperature_records tr1
group by
	cast(substring_index (substring_index (record_date, '-',-2), '-', 1) as UNSIGNED)

-------------------------------------------------------------------------------------
