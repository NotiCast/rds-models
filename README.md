# rds-models
AWS RDS models for managing devices

SQLAlchemy ORM models for use in Flask and Mailgun/HTTP API

### Pseudo-Schema

```
CREATE TABLE client (
	id PRIMARY KEY,
	is_admin TINYINT(1) NOT NULL,
);

CREATE TABLE user (
	id PRIMARY KEY,
	client_id INT NOT NULL,
	username CHAR(64) UNIQUE NOT NULL,
	password CHAR(256) NOT NULL,
);

CREATE TABLE devices2groups (
	device_id INT NOT NULL,
	group_id INT NOT NULL,
);

CREATE TABLE device (
	id PRIMARY KEY,
	arn CHAR(256) UNIQUE NOT NULL,
	name CHAR(64) NOT NULL,
	client_id INT NOT NULL,
);

CREATE TABLE group (
	id PRIMARY KEY,
	client_id INT NOT NULL,
	arn CHAR(256) UNIQUE NOT NULL,
	name CHAR(64) NOT NULL,
);
```
