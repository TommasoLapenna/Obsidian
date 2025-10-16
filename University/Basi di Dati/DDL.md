Data type:
- Numeric: smallint, integer, bigint, decimal, numeric, real, double, precision, smallserial, serial, bigserial
- Character:  character(n), char(n), varchar(n), text
- Date/Time:  timestamp, date, time, interva
- Boolean: boolean
- Geometric

Example:
```sql 
create table prova_serial(
	numero serial, nome varchar(20));
insert into prova_serial(nome) values ('Cuccureddu'), ('Perlina');
select * from prova_serial
```

Basic Constraints:
```sql
...
Stipendio1 decimal(10,2) check (stipendio>=0);
Stipendio2 decimal(10,2) CONSTRAINT stipendio_positivo
	check (Stipendio2>=0);
Matricola varchar(20) primary key
Nome varchar(50) not null
Dipartimento varchar(50) CONSTRAINT dipartimento-fk references
	Dipartimento (Codice);
...
```
Unique

Creating Table:
```sql
create table NomeTabella(
	...
);
```

Data Insert:
```sql
insert into Dipartimento values('D001', 'Amministrazione', null)
update Dipartrimento set direttore = 'AA998cc' where codice= 'D001'
```

Cascading DML actions with FK:
If an INSERT, UPDATE, DELETE statement violates an intra-relational constraint, the DMBS reports an error and the statement is not executed.
If an INSERT, UPDATE, DELETE statement violates a foreign key constraint, different actions can take place. When a foreign key constraint is created, it is possible to specify some compensating action that is executed in case the FK constraint is violated. The FK contraint identifies one internal and one external table. The constraint can be violated by a statement that acts on the internal table, on the external one or both.
- External table:
	DELETE or UPDATE a record with a value that is referenced by some rows of the internal table. In both cases it is possibile to specify some instructions that tell the DBMS how to compensate for the violation.
	- On DELETE:
		- cascade
		- set null
		- set default
		- noaction
	- On UPDATE
		- cascade
		- set null
		- set default
		- noaction
```sql
alter table Impiegato add constraint dipartimento_fk foreign key
	(Dipartimento) references
Dipartimento (Codice) ON DELETE set null ON UPDATE cascade;
```

Trigger: ^cf4d0f
```sql
create trigger strioTotale after insert on impiegato for each row
when(new.dipart is not null)
update dipartimento set stip_totale = stip_totale+new.stipendio
where numero = new.dirpart
```

```sql
after update of stipendio on impiegato
update dipartimento d set stip_totale = (select ...)
```

