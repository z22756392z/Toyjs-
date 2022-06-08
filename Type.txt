## Type

| 名子           | 類型                 | 內容                                                         | 來自     |
| -------------- | -------------------- | ------------------------------------------------------------ | -------- |
| value_type     | enum                 | value_type_null, <br>value_type_number,<br>value_type_object, | value.h  |
| object_type    | enum                 | object_type_dict,<br>object_type_list,<br>object_type_string,<br>object_type_fun | object.h |
| dict_t         | dict_entry_t *       | dict_entry_t *                                               | dict.h   |
| dict_entry     | struct               | char*  key; <br>value_t   value; <br>dict_entry_t   *pre, *next; | dict.h   |
| dict_entry_t   | strcut dict_entry    | strcut dict_entry                                            | dict.h   |
| bvalue_type    | enum                 | bvalue_type_string,<br>bvalue_type_number,                   | bvalue.h |
| bvalue         | struct               | enum bvalue_type type;<br>union  {<br>const char *string;<br> double number;<br>} | bvalue.h |
| compile_file_t | struct compiled_file | struct compiled_file                                         | vm.h     |
| compiled_file  | struct               | compiled_func_t *funcs;<br>size_t func_count;                | vm.h     |
| compiled_func  | strcut               | char *param_name;<br>unsigned char *code;<br>value_t *consts;<br>struct bvalue *bconsts;<br>size_t const_count;<br>compiled_file_t *file; | vm.h     |
| native_func_t  | function             | return value type: value_t; <br>Parameter Type:   <br>     value_t parent_scpoe, <br>     value_t arg | object.h |
| func           | struct               | struct compiled_func * compiled; <br/>native_func_t native;<br/> value_t parent_scope; | object.h |
| func_t         | func                 | func                                                         | object.h |
| object         | struct               | enum object_type type; <br>object_t *pre, *next; <br>int marked, ref count; <br>union {<br>   dict_t dict; <br>   char  * string ;<br>   func_t func;<br>} | object.h |
| object_t       | struct object        | struct object                                                | object.h |
| value          | struct               | enum value_type type; <br>union  {<br>   object_t *object;<br>   double number;<br>} | value.h  |
| value_t        | strcut value         | strcut value                                                 | value.h  |

## 補充

union和struct的區別在於：struct的各個成員會佔用不同的內存，互相之間沒有影響；而union的所有成員佔用同一段內存，修改一個成員會影響其餘所有成員。 struct佔用的內存大於等於所有成員佔用的內存的總和（成員之間可能會存在縫隙），union佔用的內存等於最長的成員佔用的內存。共用體使用了內存覆蓋技術，同一時刻只能保存一個成員的值，如果對新的成員賦值，就會把原來成員的值覆蓋掉

​	