P2-2-1-find_activities_older_than.sql

CREATE OR REPLACE FUNCTION find_activities_older_than(
    old_date DATE)
RETURNS VARCHAR(200) AS $$
    SELECT title
	FROM activity
    WHERE creation_date = old_date;
	RETURNING title
	$$
    LANGUAGE SQL;