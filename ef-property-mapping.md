-   EF asks DB wheather it can recognize and map to DB native data type.
-   If not, EF looks for a value converter.
-   If that also not exists, EF maps it as entity type which is known as navigation property.
-   If there is no setter, EF will ignore the property by convention. It thinks the property is a computed one when no setter is present. However, `private set` is fine. `modelBuilder.Entity<MyClass>.Property(p=>p.MyProperty);` can also be used to manually tell EF that it is a property despite no having no setter.  `[Required]` attribute will have no effect in the default mapping decision of setterless property.