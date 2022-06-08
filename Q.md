what is __auto_type 

```c
#define v_inc_ref(v)                                    \
    ({                                                  \
        __auto_type inc_ref__v = (v);                   \
        if ((inc_ref__v).type == value_type_object) {   \
            inc_ref__v.object->ref_count++;             \
        }                                               \
    })
```



