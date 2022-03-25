Работа с БД

CREATE TABLE имя таблицы
(
	_id int GENERATED ALWAYS AS IDENTITY NOT NULL,
	...
	
	CONSTRAINT pk_имя таблицы_имя поля_id PRIMARY KEY(имя поля_id)
	CONSTRAINT fk_имя текущей табилцы_имя таблицы на которую ссылаемся FOREIGN KEY(поле текущей таблицы) REFERENCES имя таблицы на которую ссылаемся(поле ссылаемой)
)

Добавляем автоинкремент

ALTER TABLE имя таблицы
ALTER COLUMN имя столбца
ADD GENERATED ALWAYS AS IDENTITY


Копируем таблицу

CREATE TABLE имя таблицы AS
SELECT * FROM имя таблицы


Работа с ограничениями
Найти имя ограничения

SELECT constraint_name
FROM information_schema.key_column_usage
WHERE table_name = 'имя таблицы'
	AND table_schema = 'public'
	AND column_name = 'имя столбца'

Добавить ограничение на существующую колонку
ALTER TABLE имя таблицы
ADD CONSTRAINT chk_имя таблицы_имя поля CHECK (условие с имя поля)

Удалить ограничение
ALTER TABLE имя таблицы
DROP CONSTRAINT имя ограничения

Добавить первичный ключ
ALTER TABLE имя таблицы
ADD PRIMARY KEY (имя колонки)

Добавление колонки с ограничением
ALTER TABLE имя таблицы
ADD COLUMN имя поля тип данных CONSTRAINT chk_таблица_имя поля CHECK (условие с имя поля)

Изменения:

UPDATE имя таблицы
SET колонка = значение

Функции:
Функция без возврата

CREATE OR REPLACE FUNCTION имя функции() RETURNS void AS $$
$$ LANGUAGE SQL

возврат

CREATE OR REPLACE FUNCTION имя функции() RETURNS тип AS $$
$$ LANGUAGE SQL

Функция с параметрами

CREATE OR REPLACE FUNCTION имя функции(IN имя тип, OUT имя тип) AS $$
$$ LANGUAGE SQL


CREATE OR REPLACE FUNCTION имя функции(IN имя тип, OUT имя тип) AS $$
$$ LANGUAGE SQL




