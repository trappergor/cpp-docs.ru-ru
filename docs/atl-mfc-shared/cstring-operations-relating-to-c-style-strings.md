---
title: Операции CString, связанные со строками в стиле C
ms.date: 11/04/2016
helpviewer_keywords:
- CString objects, basic operations
- MFC [C++], string handling class
- string conversion [C++], C-style strings
- strings [C++], string operations
- standard run-time library string functions
- null values, Null-terminated string conversion
- string functions
- strings [C++], in C
- string arguments
- C-style strings
- strings [C++], class CString
- casting CString objects
ms.assetid: 5048de8a-5298-4891-b8a0-c554b5a3ac1b
ms.openlocfilehash: 406a934d3691c7787085cc319770074ac2ee5926
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317950"
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>Операции CString, связанные со строками в стиле C

Объект [CString](../atl-mfc-shared/using-cstring.md) содержит данные строки символов. `CString`наследует набор [методов и операторов,](../atl-mfc-shared/reference/cstringt-class.md) которые определяются в шаблоне класса [CStringT](../atl-mfc-shared/reference/cstringt-class.md) для работы со строками данных. (`CString` это **typedef,** `CStringT` который специализируется на работе `CString` с видом символов данных, которые поддерживают.)

`CString` не обеспечивает внутреннее хранение символьных данных как строка с завершающим нулевым байтом в стиле C. Вместо этого `CString` отслеживает длину символьных данных, чтобы безопаснее контролировать эти данные и требуемое им место.

`CString` принимает строки в стиле C и предоставляет способы для доступа к символьным данным как строке в стиле C. В этом разделе содержатся следующие подразделы, в которых описано использование объекта `CString`, как если бы он являлся строкой с завершающим нулевым байтом в стиле C.

- [Преобразование в строки с завершающим нулевым байтом в стиле C](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)

- [Работа со стандартными строковыми функциями библиотеки времени выполнения](#_core_working_with_standard_run.2d.time_library_string_functions)

- [Непосредственное изменение содержимого CString](#_core_modifying_cstring_contents_directly)

- [Использование объектов CString с переменными функциями аргумента](#_core_using_cstring_objects_with_variable_argument_functions)

- [Определение формальных параметров CString](#_core_specifying_cstring_formal_parameters)

## <a name="using-cstring-as-a-c-style-null-terminated-string"></a><a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a>Использование CString в качестве C-Style Null-Terminated String

Чтобы использовать `CString` объект в качестве строки c-стиля, отбросьте объект в LPCTSTR. В следующем примере `CString` возвращает указатель на строку с завершающим нулевым байтом в стиле C, доступную только для чтения. Функция `strcpy` помещает копию строки в стиле C в переменную `myString`.

```cpp
CString aCString = "A string";
char myString[256];
strcpy(myString, (LPCTSTR)aCString);
```

Вы можете использовать методы `CString`, например `SetAt`, для изменения отдельных символов в объекте строки. Тем не менее, указатель LPCTSTR является временным и `CString`становится недействительным, когда любые изменения сделаны в . `CString` также может выйти за пределы области, после чего выполняется его автоматическое удаление. Мы рекомендуем вам получить свежий указатель `CString` LPCTSTR объекта каждый раз, когда вы используете один.

Иногда вам может потребоваться копия данных `CString` для непосредственного внесения изменений. Используйте более защищенную функцию `strcpy_s` (или переносимую между Юникодом и многобайтовой кодировкой `_tcscpy_s`) для копирования объекта `CString` в отдельный буфер. Именно здесь можно безопасно изменить символы, как показано в следующем примере.

[!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]

> [!NOTE]
> Третий аргумент `strcpy_s` (или Unicode / MBCS-портативный) `_tcscpy_s`является либо `const char*` `const wchar_t*` (Unicode) или (ANSI). Приведенный выше пример передает `CString` для этого аргумента. Компилятор C++ автоматически применяет функцию преобразования, определенную для класса `CString`, который преобразует `CString` в `LPCTSTR`. Возможность определения операций приведения от одного типа к другому — это одна из самых полезных особенностей C++.

## <a name="working-with-standard-run-time-library-string-functions"></a><a name="_core_working_with_standard_run.2d.time_library_string_functions"></a>Работа со стандартными функциями строки библиотеки Run-Time

Вы должны иметь возможность найти метод `CString` для выполнения строковой операции, для которой может потребоваться использование стандартных строковых функций библиотеки времени выполнения, таких как `strcmp` (или переносимой между Юникодом и многобайтовой кодировкой `_tcscmp`).

Если необходимо использовать функции строки c run-time, вы можете использовать методы, описанные в _core_using_cstring_as_a_c.2d.style_null.2d.terminated_string. Вы можете скопировать объект `CString` в эквивалентный строковый буфер в стиле C, выполнить операции в этом буфере, а затем снова назначить полученную строку в стиле C объекту `CString`.

## <a name="modifying-cstring-contents-directly"></a><a name="_core_modifying_cstring_contents_directly"></a>Изменение содержимого CString непосредственно

В большинстве ситуаций для изменения содержимого объекта `CString` или для преобразования `CString` в символьную строку в стиле C следует использовать функции-члены `CString`.

В некоторых ситуациях имеет смысл напрямую изменить содержимое `CString`, например, при работе с функциями операционной системы, требующими символьный буфер.

Методы `GetBuffer` и `ReleaseBuffer` предоставляют доступ к внутреннему символьному буферу объекта `CString` и позволяют изменять его напрямую. Приведенные ниже действия показывают, как использовать такие функции в этих целях.

### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>Использование GetBuffer и ReleaseBuffer для доступа к внутреннему символьному буферу объекта CString

1. Вызовите `GetBuffer` для объекта `CString` и укажите требуемую длину буфера.

1. Используйте указатель, возвращенный `GetBuffer`, для записи символов напрямую в объект `CString`.

1. Вызовите `ReleaseBuffer` для объекта `CString`, чтобы обновить все внутренние сведения о состоянии `CString`, например длину строки. После непосредственного изменения содержимого объекта `CString` необходимо вызвать `ReleaseBuffer` до вызова любых других функций-членов `CString`.

## <a name="using-cstring-objects-with-variable-argument-functions"></a><a name="_core_using_cstring_objects_with_variable_argument_functions"></a>Использование объектов CString с переменными функциями аргумента

Некоторые функции C принимают переменное число аргументов. Ярким примером этого является `printf_s`. Из-за способа объявления этого вида функции компилятор не может быть уверен в типе аргументов и не может определить, какую операцию преобразования требуется выполнить для каждого аргумента. Таким образом, вам важно использовать явное приведение типа при передаче объекта `CString` в функцию, которая принимает переменное число аргументов.

Чтобы использовать `CString` объект в функции переменной `CString` аргументации, явно отбросьте строку LPCTSTR, как показано в следующем примере.

[!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]

## <a name="specifying-cstring-formal-parameters"></a><a name="_core_specifying_cstring_formal_parameters"></a>Определение формальных параметров CString

Для большинства функций, которым требуется строковый аргумент, в прототипе функции в качестве указателя `const` на символ (`LPCTSTR`) вместо `CString` лучше всего указать формальный параметр. Когда формальный параметр `const` указан в качестве указателя на символ, вы можете передать либо указатель`"hi there"`на массив `CString` TCHAR, буквальную строку, или объект. Объект `CString` будет автоматически преобразован в LPCTSTR. В любом месте вы можете использовать LPCTSTR, вы также можете использовать `CString` объект.

Вы также можете указать формальный параметр в `const CString&`качестве постоянной ссылки строки (т.е.), если аргумент не будет изменен. Бросьте конст-модификатор, если строка будет изменена функцией. **const** Если требуется использовать по умолчанию значение NULL, инициализируйте его с нулевой строкой [`""`], как показано ниже:

[!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]

Для большинства результатов функции вы можете просто возвратить объект `CString` по значению.

## <a name="see-also"></a>См. также раздел

[Струны (ATL/MFC)](../atl-mfc-shared/strings-atl-mfc.md)<br/>
[CString Аргумент Прохождение](../atl-mfc-shared/cstring-argument-passing.md)
