# Operations

## Description

An operation creates records, inserts records or exports records in text format (e.g. JSON).

## Definitions

~~~
create <EntityAlias> : (
	[ group(<Groupidentifier>) ]
)

insert <EntityAlias> : (
	destination(<DestinationIdentifier>)
	[ group(<GroupIdentifier>) ]
)

export <EntityAlias> : (
	destination(<DestinationIdentifier>)
	type( { json | csv } )
	[ group(<GroupIdentifier>) ]
)
~~~

## Notes

* The `<EntityAlias>` refers to an entity defined in the same repository.
* A `create` operation may be used many times in a repository,
generating new records of the entity.
* An `insert` operation inserts the created records into the destination.
* If an `insert` operation is called without any previous `create` operation
of the same `<EntityAlias>`, Dadela will execute a `create` operation before the `insert`.
* If the `group` parameter is used on `create`, the created records are related to this group.
* If the `group` parameter is used on `insert` or `export`,
the inserted/exported records are retrieved from this group.

## Examples

~~~
create MyBigAccounts: (group(GroupA)),
insert MyBigAccounts: (
 	destination(MyDestination1) group(GroupA)
),
export MyBigAccounts: (
	destination(MyDestination2) group(GroupA)
),
~~~