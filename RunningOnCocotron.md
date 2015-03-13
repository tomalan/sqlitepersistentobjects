# Introduction #

Starting from [r31](https://code.google.com/p/sqlitepersistentobjects/source/detail?r=31), sqlitepersistentobjects has support for [Cocotron](http://www.cocotron.org) runtime. The only critical issue is that there are no ways for properties introspection in Cocotron, so you have to add more magic to your models to make them work.

# Details #

For each descendant of SQLitePersistentObject you must implement + (NSArray **)getPropertiesList like this:
```
+ (NSArray *)getPropertiesList
{
        return [NSArray arrayWithObjects:
                [NSArray arrayWithObjects:@"name", @"@\"NSString\"", nil],
                [NSArray arrayWithObjects:@"favoriteInt", @"i", nil],
                [NSArray arrayWithObjects:@"birthDate", @"@\"NSDate\"", nil],
        nil];
}
```
For each property you return NSArray with property name and property type (for allowed types see SQLitePersistentObject.h).**

To simplify typing you can use the following macros in your @implementation:
```
DECLARE_PROPERTIES (
	DECLARE_PROPERTY(@"name",		@"@\"NSString *\""),
	DECLARE_PROPERTY(@"favoriteInt",	@"i"),
	DECLARE_PROPERTY(@"bithDate",		@"@\"NSDate *\"")
)
```
It will generate complete getPropertiesList selector implementation like in the snippet above.