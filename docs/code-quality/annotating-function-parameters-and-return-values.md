---
title: Добавление заметок к параметрам и возвращаемым значениям функций
description: Справочное руководство по заметкам параметров функции и возвращаемого значения.
ms.date: 10/15/2019
ms.topic: conceptual
f1_keywords:
- _Outptr_opt_result_bytebuffer_to_
- _Inout_updates_all_opt_
- _Post_equal_to_
- _Outptr_opt_result_maybenull_
- _Out_writes_bytes_all_
- _Out_writes_all_opt_
- _In_opt_
- _Outptr_
- _Outptr_result_maybenull_
- _Outref_result_bytebuffer_all_maybenull_
- _Inout_updates_opt_z_
- _Inout_updates_z_
- _Out_writes_
- _Out_writes_to_ptr_opt_z_
- _In_reads_to_ptr_opt_
- _Ret_writes_to_maybenull_
- _Outref_result_maybenull_
- _Ret_writes_bytes_
- _Outptr_result_bytebuffer_
- _Out_writes_opt_
- _Inout_updates_bytes_opt_
- _In_z_
- _Inout_updates_to_
- _Ret_maybenull_
- _Ret_writes_bytes_to_
- _Ret_z_
- _COM_Outptr_
- _Ret_maybenull_z_
- _Out_opt_
- _In_reads_opt_z_
- _Outptr_result_bytebuffer_to_
- _Ret_notnull_
- _COM_Outptr_opt_result_maybenull_
- _Inout_updates_to_opt_
- _Inout_updates_
- _Outptr_opt_result_buffer_
- _Outptr_result_buffer_to_
- _Out_writes_to_ptr_opt_
- _Out_writes_bytes_all_opt_
- _Inout_updates_all_
- _Deref_inout_range_
- _Ret_writes_
- _Out_writes_z_
- _Ret_writes_to_
- _Out_writes_to_ptr_z_
- _Out_writes_bytes_to_opt_
- _In_reads_or_z_
- _Inout_updates_bytes_to_
- _In_reads_z_
- _In_opt_z_
- _Outref_result_buffer_maybenull_
- _Ret_range_
- _COM_Outptr_opt_
- _Outptr_opt_result_maybenull_z_
- _In_reads_opt_
- _Inout_
- _Field_range_
- _Ret_writes_z_
- _Out_writes_to_
- _Out_writes_to_ptr_
- _Inout_opt_z_
- _Outref_
- _Deref_out_range_
- _Outref_result_buffer_
- _Outref_result_buffer_to_
- _Outref_result_bytebuffer_to_maybenull_
- _In_reads_bytes_
- _Outptr_opt_result_buffer_to_
- _Outref_result_buffer_all_
- _Out_writes_bytes_to_
- _Result_zeroonfailure_
- _In_reads_bytes_opt_
- _Outref_result_buffer_to_maybenull_
- _Outref_result_bytebuffer_all_
- _Outref_result_buffer_all_maybenull_
- _Ret_writes_maybenull_z_
- _In_range_
- _Inout_updates_bytes_all_opt_
- _Outref_result_bytebuffer_to_
- _Inout_updates_bytes_to_opt_
- _Pre_equal_to_
- _Ret_writes_bytes_maybenull_
- _COM_Outptr_result_maybenull_
- _Ret_writes_maybenull_
- _Out_writes_bytes_
- _Outptr_opt_
- _Out_writes_opt_z_
- _Outref_result_nullonfailure_
- _Outptr_opt_result_z_
- _Inout_opt_
- _Deref_in_range_
- _Outptr_result_z_
- _In_reads_to_ptr_opt_z_
- _Struct_size_bytes_
- _Outptr_result_nullonfailure_
- _In_
- _Inout_updates_bytes_
- _In_reads_to_ptr_z_
- _Ret_writes_bytes_to_maybenull
- _Outptr_opt_result_nullonfailure_
- _In_reads_to_ptr_
- _Outptr_result_buffer_
- _Out_
- _Outref_result_bytebuffer_maybenull_
- _Outptr_result_maybenull_z_
- _In_reads_
- _Inout_updates_opt_
- _Out_writes_to_opt_
- _Outptr_opt_result_bytebuffer_
- _Out_writes_all_
- _Out_range_
- _Inout_updates_bytes_all_
- _Inout_z_
- _Outref_result_bytebuffer_
- _Result_nullonfailure_
- _Ret_null_
- _Scanf_format_string_
- _Scanf_s_format_string_
- _Printf_format_string_
ms.assetid: 82826a3d-0c81-421c-8ffe-4072555dca3a
ms.openlocfilehash: 4d0325fbab2f27da2556e2c252e35711d9b42789
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87231264"
---
# <a name="annotating-function-parameters-and-return-values"></a>Добавление заметок к параметрам и возвращаемым значениям функций

В этой статье описывается типичное использование заметок для простых параметров функции — скаляров и указателей на структуры и классы — и большинства типов буферов. В этой статье также показаны распространенные шаблоны использования для заметок. Дополнительные примечания, связанные с функциями, см. в разделе [Аннотирование поведения функций](../code-quality/annotating-function-behavior.md).

## <a name="pointer-parameters"></a>Параметры указателя

Для заметок, приведенных в следующей таблице, если параметр указателя снабжен заметками, анализатор сообщает об ошибке, если указатель имеет значение null. Эта заметка применяется к указателям и к любому элементу данных, на который указывает.

### <a name="annotations-and-descriptions"></a>Аннотации и описания

- `_In_`

     Закомментировать входные параметры, которые являются скалярными, структурами, указателями на структуры и т. д. Явно можно использовать для простых скаляров. Параметр должен быть допустимым в предварительном состоянии и не будет изменен.

- `_Out_`

     Закомментировать выходные параметры, которые являются скалярными, структурами, указателями на структуры и т. д. Не применяйте эту аннотацию к объекту, который не может вернуть значение, например скаляр, передаваемый по значению. Параметр не должен быть допустимым в предварительном состоянии, но должен быть допустимым в состоянии после.

- `_Inout_`

     Заметка параметра, который будет изменен функцией. Он должен быть допустимым как в предварительном, так и после состояния, но предполагается, что они имеют разные значения до и после вызова. Необходимо применить к изменяемому значению.

- `_In_z_`

     Указатель на строку, завершающуюся нулем, которая используется в качестве входных данных. Строка должна быть допустимой в предварительном состоянии. `PSTR`Предпочтительными являются варианты, которые уже имеют нужные заметки.

- `_Inout_z_`

     Указатель на массив символов, заканчивающийся нулем, который будет изменен. Он должен быть допустимым до и после вызова, но предполагается, что значение изменилось. Конечный символ NULL можно переместить, но доступ к элементам может осуществляться только до исходного нулевого терминатора.

- `_In_reads_(s)`

     `_In_reads_bytes_(s)`

     Указатель на массив, который считывается функцией. Массив имеет размер `s` элементов, все из которых должны быть допустимыми.

     `_bytes_`Вариант задает размер в байтах вместо элементов. Используйте этот вариант, только если размер не может быть выражен как элемент. Например, **`char`** строки будут использовать `_bytes_` вариант только в том случае, если аналогичная функция использует **`wchar_t`** .

- `_In_reads_z_(s)`

     Указатель на массив, заканчивающийся нулем и имеющий известный размер. Элементы вплоть до нулевого терминатора — или, `s` Если нет терминатора null, должны быть допустимы в предварительном состоянии. Если размер известен в байтах, масштабируется `s` по размеру элемента.

- `_In_reads_or_z_(s)`

     Указатель на массив, заканчивающийся нулем или имеющий известный размер или оба. Элементы вплоть до нулевого терминатора — или, `s` Если нет терминатора null, должны быть допустимы в предварительном состоянии. Если размер известен в байтах, масштабируется `s` по размеру элемента. (Используется для `strn` семейства.)

- `_Out_writes_(s)`

     `_Out_writes_bytes_(s)`

     Указатель на массив `s` элементов (отв. bytes), который будет записан функцией. Элементы массива не должны быть допустимыми в предварительном состоянии, а количество элементов, допустимых в состоянии после, не указано. Если в типе параметра есть аннотации, они применяются в состоянии после. Например, рассмотрим следующий код.

     ```cpp
     typedef _Null_terminated_ wchar_t *PWSTR;
     void MyStringCopy(_Out_writes_(size) PWSTR p1, _In_ size_t size, _In_ PWSTR p2);
     ```

     В этом примере вызывающий объект предоставляет буфер `size` элементов для `p1` . `MyStringCopy`делает некоторые из этих элементов допустимыми. Что более важно, `_Null_terminated_` заметка на `PWSTR` означает, что `p1` завершается нулем в состоянии после. Таким образом, количество допустимых элементов по-прежнему четко определено, но конкретный счетчик элементов не требуется.

     `_bytes_`Вариант задает размер в байтах вместо элементов. Используйте этот вариант, только если размер не может быть выражен как элемент. Например, **`char`** строки будут использовать `_bytes_` вариант только в том случае, если аналогичная функция использует **`wchar_t`** .

- `_Out_writes_z_(s)`

     Указатель на массив `s` элементов. Элементы не обязательно должны быть допустимыми в предварительном состоянии. В состоянии после состояния элементы, находящиеся вплоть до конца null, должны быть допустимыми. Если размер известен в байтах, масштабируется `s` по размеру элемента.

- `_Inout_updates_(s)`

     `_Inout_updates_bytes_(s)`

     Указатель на массив, который считывается и записывается в функцию. Она имеет размер `s` элементов и допустима в предварительном и после состояния.

     `_bytes_`Вариант задает размер в байтах вместо элементов. Используйте этот вариант, только если размер не может быть выражен как элемент. Например, **`char`** строки будут использовать `_bytes_` вариант только в том случае, если аналогичная функция использует **`wchar_t`** .

- `_Inout_updates_z_(s)`

     Указатель на массив, заканчивающийся нулем и имеющий известный размер. Элементы вплоть до нулевого терминатора, который должен присутствовать, должны быть допустимыми как перед, так и после состояния. Предполагается, что значение в состоянии после состояния отличается от значения в предварительном состоянии; , включающее расположение терминатора null. Если размер известен в байтах, масштабируется `s` по размеру элемента.

- `_Out_writes_to_(s,c)`

     `_Out_writes_bytes_to_(s,c)`

     `_Out_writes_all_(s)`

     `_Out_writes_bytes_all_(s)`

     Указатель на массив `s` элементов. Элементы не обязательно должны быть допустимыми в предварительном состоянии. В состоянии после состояния элементы вплоть до `c` элемента-th должны быть допустимыми. `_bytes_`Вариант можно использовать, если размер известен в байтах, а не в количестве элементов.

     Пример:

     ```cpp
     void *memcpy(_Out_writes_bytes_all_(s) char *p1, _In_reads_bytes_(s) char *p2, _In_ int s);
     void *wordcpy(_Out_writes_all_(s) DWORD *p1, _In_reads_(s) DWORD *p2, _In_ int s);
     ```

- `_Inout_updates_to_(s,c)`

     `_Inout_updates_bytes_to_(s,c)`

     Указатель на массив, который считывается и записывается функцией. Это `s` элементы размера, все из которых должны быть допустимы в предварительном состоянии, а `c` элементы должны быть допустимыми в состоянии после.

     `_bytes_`Вариант задает размер в байтах вместо элементов. Используйте этот вариант, только если размер не может быть выражен как элемент. Например, **`char`** строки будут использовать `_bytes_` вариант только в том случае, если аналогичная функция использует **`wchar_t`** .

- `_Inout_updates_all_(s)`

     `_Inout_updates_bytes_all_(s)`

     Указатель на массив, который считывается и записывается функцией размера `s` элементов. Определяется как эквивалент:

     `_Inout_updates_to_(_Old_(s), _Old_(s))    _Inout_updates_bytes_to_(_Old_(s), _Old_(s))`

     Иными словами, каждый элемент, существующий в буфере вплоть до `s` в предварительном состоянии, допустим в предварительном состоянии и после состояния.

     `_bytes_`Вариант задает размер в байтах вместо элементов. Используйте этот вариант, только если размер не может быть выражен как элемент. Например, **`char`** строки будут использовать `_bytes_` вариант только в том случае, если аналогичная функция использует **`wchar_t`** .

- `_In_reads_to_ptr_(p)`

     Указатель на массив, для которого `p - _Curr_` (то есть `p` минус `_Curr_` ) является допустимым выражением. Элементы перед `p` должны быть допустимыми в предварительном состоянии.

    Пример:

    ```cpp
    int ReadAllElements(_In_reads_to_ptr_(EndOfArray) const int *Array, const int *EndOfArray);
    ```

- `_In_reads_to_ptr_z_(p)`

     Указатель на массив, заканчивающийся нулем, для которого выражение `p - _Curr_` (то есть `p` минус `_Curr_` ) является допустимым выражением. Элементы перед `p` должны быть допустимыми в предварительном состоянии.

- `_Out_writes_to_ptr_(p)`

     Указатель на массив, для которого `p - _Curr_` (то есть `p` минус `_Curr_` ) является допустимым выражением. Элементы перед `p` не должны быть допустимыми в предварительном состоянии и должны быть допустимыми в состоянии после.

- `_Out_writes_to_ptr_z_(p)`

     Указатель на массив, заканчивающийся нулем, для которого `p - _Curr_` (то есть `p` минус `_Curr_` ) является допустимым выражением. Элементы перед `p` не должны быть допустимыми в предварительном состоянии и должны быть допустимыми в состоянии после.

## <a name="optional-pointer-parameters"></a>Необязательные параметры указателя

Если заметка параметра указателя включает `_opt_` , то она указывает, что параметр может иметь значение null. В противном случае заметка ведет себя так же, как и версия, которая не содержит `_opt_` . Ниже приведен список `_opt_` вариантов заметок к параметрам указателя:

:::row:::
    :::column:::
        `_In_opt_`<br /><br /> `_Out_opt_`<br /><br /> `_Inout_opt_`<br /><br /> `_In_opt_z_`<br /><br /> `_Inout_opt_z_`<br /><br /> `_In_reads_opt_`<br /><br /> `_In_reads_bytes_opt_`<br /><br /> `_In_reads_opt_z_`
    :::column-end:::
    :::column:::
        `_Out_writes_opt_`<br /><br /> `_Out_writes_opt_z_`<br /><br /> `_Inout_updates_opt_`<br /><br /> `_Inout_updates_bytes_opt_`<br /><br /> `_Inout_updates_opt_z_`<br /><br /> `_Out_writes_to_opt_`<br /><br /> `_Out_writes_bytes_to_opt_`<br /><br /> `_Out_writes_all_opt_`<br /><br /> `_Out_writes_bytes_all_opt_`
    :::column-end:::
    :::column:::
        `_Inout_updates_to_opt_`<br /><br /> `_Inout_updates_bytes_to_opt_`<br /><br /> `_Inout_updates_all_opt_`<br /><br /> `_Inout_updates_bytes_all_opt_`<br /><br /> `_In_reads_to_ptr_opt_`<br /><br /> `_In_reads_to_ptr_opt_z_`<br /><br /> `_Out_writes_to_ptr_opt_`<br /><br /> `_Out_writes_to_ptr_opt_z_`
    :::column-end:::
:::row-end:::

## <a name="output-pointer-parameters"></a>Выходные параметры указателя

Для параметров выходного указателя требуется специальная нотация для неоднозначности значения NULL в параметре и расположении, на которое указывает.

### <a name="annotations-and-descriptions"></a>Аннотации и описания

- `_Outptr_`

   Параметр не может иметь значение null, а в состоянии после состояния значение расположения "указывает на" не может быть равно NULL и должно быть допустимым.

- `_Outptr_opt_`

   Параметр может иметь значение null, но в состоянии после состояния значение расположения "указывает на" не может быть равно NULL и должно быть допустимым.

- `_Outptr_result_maybenull_`

   Параметр не может иметь значение null, а в состоянии после состояния значение расположения "указывает на" может быть равно null.

- `_Outptr_opt_result_maybenull_`

   Параметр может иметь значение null, а в состоянии после состояния значение расположения "указывает на" может быть равно null.

  В следующей таблице дополнительные подстроки вставляются в имя заметки, чтобы уточнить смысл заметки. Различные подстроки: `_z` , `_COM_` , `_buffer_` , `_bytebuffer_` и `_to_` .

> [!IMPORTANT]
> Если интерфейс, с которым записываются заметки, является COM, используйте COM-форму этих заметок. Не используйте аннотации COM с любым другим интерфейсом типа.

- `_Outptr_result_z_`

   `_Outptr_opt_result_z_`

   `_Outptr_result_maybenull_z_`

   `_Outptr_opt_result_maybenull_z_`

   Возвращаемый указатель имеет `_Null_terminated_` заметку.

- `_COM_Outptr_`

   `_COM_Outptr_opt_`

   `_COM_Outptr_result_maybenull_`

   `_COM_Outptr_opt_result_maybenull_`

   Возвращаемый указатель имеет семантику COM, поэтому он несет оператор `_On_failure_` POST, что возвращаемый указатель имеет значение null.

- `_Outptr_result_buffer_(s)`

   `_Outptr_result_bytebuffer_(s)`

   `_Outptr_opt_result_buffer_(s)`

   `_Outptr_opt_result_bytebuffer_(s)`

   Возвращаемый указатель указывает на допустимый буфер элементов размера `s` или байтов.

- `_Outptr_result_buffer_to_(s, c)`

   `_Outptr_result_bytebuffer_to_(s, c)`

   `_Outptr_opt_result_buffer_to_(s,c)`

   `_Outptr_opt_result_bytebuffer_to_(s,c)`

   Возвращаемый указатель указывает на буфер `s` элементов размера или байтов, из которых первый `c` допустимым.

Некоторые соглашения об интерфейсе предполагают, что выходные параметры обнулить при сбое. За исключением явного COM-кода, рекомендуется использовать формы в следующей таблице. Для COM-кода используйте соответствующие формы COM, перечисленные в предыдущем разделе.

- `_Result_nullonfailure_`

   Изменяет другие заметки. Если функция завершается с ошибкой, в результате устанавливается значение null.

- `_Result_zeroonfailure_`

   Изменяет другие заметки. Если функция завершается с ошибкой, в результате устанавливается нулевое значение.

- `_Outptr_result_nullonfailure_`

   Возвращаемый указатель указывает на допустимый буфер, если функция завершается успешно, или значение null, если функция завершается ошибкой. Эта заметка предназначена для необязательного параметра.

- `_Outptr_opt_result_nullonfailure_`

   Возвращаемый указатель указывает на допустимый буфер, если функция завершается успешно, или значение null, если функция завершается ошибкой. Эта заметка предназначена для необязательного параметра.

- `_Outref_result_nullonfailure_`

   Возвращаемый указатель указывает на допустимый буфер, если функция завершается успешно, или значение null, если функция завершается ошибкой. Эта заметка предназначена для ссылочного параметра.

## <a name="output-reference-parameters"></a>Выходные параметры ссылки

Параметр ссылки обычно используется для выходных параметров. Для простых выходных ссылочных параметров, таких как `int&` , `_Out_` предоставляет правильную семантику. Однако если выходное значение является указателем, таким как `int *&` , то эквивалентные заметки указателя, такие как, `_Outptr_ int **` не обеспечивают правильную семантику. Для краткого выражения семантики выходных параметров выходной ссылки для типов указателей используйте следующие составные аннотации:

### <a name="annotations-and-descriptions"></a>Аннотации и описания

- `_Outref_`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null.

- `_Outref_result_maybenull_`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии после.

- `_Outref_result_buffer_(s)`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null. Указывает на допустимый буфер `s` элементов размера.

- `_Outref_result_bytebuffer_(s)`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null. Указывает на допустимый буфер размера в `s` байтах.

- `_Outref_result_buffer_to_(s, c)`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null. Указывает на буфер `s` элементов, из которых первый `c` допустимым.

- `_Outref_result_bytebuffer_to_(s, c)`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null. Указывает на буфер `s` байтов, из которых первый `c` допустимым.

- `_Outref_result_buffer_all_(s)`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null. Указывает на допустимый буфер `s` допустимого размера элементов.

- `_Outref_result_bytebuffer_all_(s)`

     Результат должен быть допустимым в состоянии POST и не может иметь значение null. Указывает на допустимый буфер `s` байтов допустимых элементов.

- `_Outref_result_buffer_maybenull_(s)`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии после. Указывает на допустимый буфер `s` элементов размера.

- `_Outref_result_bytebuffer_maybenull_(s)`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии после. Указывает на допустимый буфер размера в `s` байтах.

- `_Outref_result_buffer_to_maybenull_(s, c)`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии после. Указывает на буфер `s` элементов, из которых первый `c` допустимым.

- `_Outref_result_bytebuffer_to_maybenull_(s,c)`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии POST. Указывает на буфер `s` байтов, из которых первый `c` допустимым.

- `_Outref_result_buffer_all_maybenull_(s)`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии POST. Указывает на допустимый буфер `s` допустимого размера элементов.

- `_Outref_result_bytebuffer_all_maybenull_(s)`

     Результат должен быть допустимым в состоянии после состояния, но может иметь значение NULL в состоянии POST. Указывает на допустимый буфер `s` байтов допустимых элементов.

## <a name="return-values"></a>Возвращаемые значения

Возвращаемое значение функции напоминает `_Out_` параметр, но находится на другом уровне разыменования, и вам не нужно учитывать концепцию указателя на результат. Для следующих заметок возвращаемое значение является объектом с заметками — скаляром, указателем на структуру или указателем на буфер. Эти заметки имеют ту же семантику, что и соответствующая `_Out_` Аннотация.

:::row:::
    :::column:::
        `_Ret_z_`<br /><br /> `_Ret_writes_(s)`<br /><br /> `_Ret_writes_bytes_(s)`<br /><br /> `_Ret_writes_z_(s)`<br /><br /> `_Ret_writes_to_(s,c)`<br /><br /> `_Ret_writes_maybenull_(s)`<br /><br /> `_Ret_writes_to_maybenull_(s)`<br /><br /> `_Ret_writes_maybenull_z_(s)`
    :::column-end:::
    :::column:::
        `_Ret_maybenull_`<br /><br /> `_Ret_maybenull_z_`<br /><br /> `_Ret_null_`<br /><br /> `_Ret_notnull_`<br /><br /> `_Ret_writes_bytes_to_`<br /><br /> `_Ret_writes_bytes_maybenull_`<br /><br /> `_Ret_writes_bytes_to_maybenull_`
    :::column-end:::
:::row-end:::

## <a name="format-string-parameters"></a>Параметры строки форматирования

- `_Printf_format_string_`Указывает, что параметр является строкой формата для использования в `printf` выражении.

     **Пример**

    ```cpp
    int MyPrintF(_Printf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwprintf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_format_string_`Указывает, что параметр является строкой формата для использования в `scanf` выражении.

     **Пример**

    ```cpp
    int MyScanF(_Scanf_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf(format, args);
           va_end(args);
           return ret;
    }
    ```

- `_Scanf_s_format_string_`Указывает, что параметр является строкой формата для использования в `scanf_s` выражении.

     **Пример**

    ```cpp
    int MyScanF_s(_Scanf_s_format_string_ const wchar_t* format, ...)
    {
           va_list args;
           va_start(args, format);
           int ret = vwscanf_s(format, args);
           va_end(args);
           return ret;
    }
    ```

## <a name="other-common-annotations"></a>Другие общие заметки

### <a name="annotations-and-descriptions"></a>Аннотации и описания

- `_In_range_(low, hi)`

     `_Out_range_(low, hi)`

     `_Ret_range_(low, hi)`

     `_Deref_in_range_(low, hi)`

     `_Deref_out_range_(low, hi)`

     `_Deref_inout_range_(low, hi)`

     `_Field_range_(low, hi)`

     Параметр, поле или результат находятся в диапазоне (включительно) от `low` до `hi` . Эквивалентно `_Satisfies_(_Curr_ >= low && _Curr_ <= hi)` , применяется к объекту с заметками вместе с соответствующими условиями предварительного или поступающего состояния.

    > [!IMPORTANT]
    > Хотя имена содержат "in" и "out", семантика `_In_` и `_Out_` **не** применяются к этим заметкам.

- `_Pre_equal_to_(expr)`

     `_Post_equal_to_(expr)`

     Заметка имеет значение в точности `expr` . Эквивалентно `_Satisfies_(_Curr_ == expr)` , применяется к объекту с заметками вместе с соответствующими условиями предварительного или поступающего состояния.

- `_Struct_size_bytes_(size)`

     Применяется к объявлению структуры или класса. Указывает, что допустимый объект этого типа может быть больше, чем объявленный тип, с числом байтов, предоставленным `size` . Пример:

     `typedef _Struct_size_bytes_(nSize) struct MyStruct {    size_t nSize;    ... };`

     Затем размер буфера в байтах параметра `pM` типа принимает `MyStruct *` значение:

     `min(pM->nSize, sizeof(MyStruct))`

## <a name="see-also"></a>См. также раздел

- [Использование аннотаций SAL для сокращения количества дефектов в коде C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Основные сведения о языке SAL](../code-quality/understanding-sal.md)
- [Аннотация поведения функций](../code-quality/annotating-function-behavior.md)
- [Аннотация структур и классов](../code-quality/annotating-structs-and-classes.md)
- [Аннотация поведения блокировки](../code-quality/annotating-locking-behavior.md)
- [Указание времени и места применения примечания](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Встроенные функции](../code-quality/intrinsic-functions.md)
- [Рекомендации и примеры](../code-quality/best-practices-and-examples-sal.md)
