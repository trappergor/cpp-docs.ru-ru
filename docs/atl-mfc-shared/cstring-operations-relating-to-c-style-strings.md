---
title: "Операции CString, связанные с строки в стиле C | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 04be31fa3209aace6fd5446532510e2a27e6bdce
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cstring-operations-relating-to-c-style-strings"></a>Операции CString, связанные со строками в стиле C
Объект [CString](../atl-mfc-shared/using-cstring.md) объект содержит символьных строковых данных. `CString`наследует набор [методы и операторы](../atl-mfc-shared/reference/cstringt-class.md) , определенные в шаблоне класса [CStringT](../atl-mfc-shared/reference/cstringt-class.md) для работы со строковыми данными. (`CString` — `typedef` , специализирующейся `CStringT` для работы с типом символьных данных, `CString` поддерживает.)  
  
 `CString` не обеспечивает внутреннее хранение символьных данных как строка с завершающим нулевым байтом в стиле C. Вместо этого `CString` отслеживает длину символьных данных, чтобы безопаснее контролировать эти данные и требуемое им место.  
  
 `CString` принимает строки в стиле C и предоставляет способы для доступа к символьным данным как строке в стиле C. В этом разделе содержатся следующие подразделы, в которых описано использование объекта `CString`, как если бы он являлся строкой с завершающим нулевым байтом в стиле C.  
  
- [Преобразование в стиле C нулем строк](#_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string)  
  
- [Работа со строковыми функциями стандартной библиотеки времени выполнения](#_core_working_with_standard_run.2d.time_library_string_functions)  
  
- [Непосредственное изменение содержимого CString](#_core_modifying_cstring_contents_directly)  
  
- [Использование объектов CString с функциями аргументов переменных](#_core_using_cstring_objects_with_variable_argument_functions)  
  
- [Указание формальных параметров CString](#_core_specifying_cstring_formal_parameters)  
  
##  <a name="_core_using_cstring_as_a_c.2d.style_null.2d.terminated_string"></a>Использование CString в стиле языка C, идентифицирующий  
 Чтобы использовать объект `CString` в качестве строки в стиле C, выполните приведение этого объекта к `LPCTSTR`. В следующем примере `CString` возвращает указатель на строку с завершающим нулевым байтом в стиле C, доступную только для чтения. Функция `strcpy` помещает копию строки в стиле C в переменную `myString`.  
  
```  
CString aCString = "A string";  
char myString[256];  
strcpy(myString, (LPCTSTR)aCString);
```  
  
 Вы можете использовать методы `CString`, например `SetAt`, для изменения отдельных символов в объекте строки. Однако указатель `LPCTSTR` является временным и становится недействительным при любом изменении `CString`. `CString` также может выйти за пределы области, после чего выполняется его автоматическое удаление. Мы рекомендуем получать новый указатель `LPCTSTR` объекта `CString` каждый раз, когда он используется.  
  
 Иногда вам может потребоваться копия данных `CString` для непосредственного внесения изменений. Используйте более защищенную функцию `strcpy_s` (или переносимую между Юникодом и многобайтовой кодировкой `_tcscpy_s`) для копирования объекта `CString` в отдельный буфер. Именно здесь можно безопасно изменить символы, как показано в следующем примере.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#189](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_1.cpp)]  
  
> [!NOTE]
>  Третий аргумент `strcpy_s` (или переносимой между Юникодом и многобайтовой Кодировки- `_tcscpy_s`) либо `const wchar_t*` (Юникод) или `const char*` (ANSI). Приведенный выше пример передает `CString` для этого аргумента. Компилятор C++ автоматически применяет функцию преобразования, определенную для класса `CString`, который преобразует `CString` в `LPCTSTR`. Возможность определения операций приведения от одного типа к другому — это одна из самых полезных особенностей C++.  
  
##  <a name="_core_working_with_standard_run.2d.time_library_string_functions"></a>Работа со строковыми функциями стандартной библиотеки времени выполнения  
 Вы должны иметь возможность найти метод `CString` для выполнения строковой операции, для которой может потребоваться использование стандартных строковых функций библиотеки времени выполнения, таких как `strcmp` (или переносимой между Юникодом и многобайтовой кодировкой `_tcscmp`).  
  
 Если необходимо использовать функции строку времени выполнения C, можно использовать методики, описанные в _core_using_cstring_as_a_c.2d.style_null.2d.terminated_string. Вы можете скопировать объект `CString` в эквивалентный строковый буфер в стиле C, выполнить операции в этом буфере, а затем снова назначить полученную строку в стиле C объекту `CString`.  
  
##  <a name="_core_modifying_cstring_contents_directly"></a>Непосредственное изменение содержимого CString  
 В большинстве ситуаций для изменения содержимого объекта `CString` или для преобразования `CString` в символьную строку в стиле C следует использовать функции-члены `CString`.  
  
 В некоторых ситуациях имеет смысл напрямую изменить содержимое `CString`, например, при работе с функциями операционной системы, требующими символьный буфер.  
  
 Методы `GetBuffer` и `ReleaseBuffer` предоставляют доступ к внутреннему символьному буферу объекта `CString` и позволяют изменять его напрямую. Приведенные ниже действия показывают, как использовать такие функции в этих целях.  
  
#### <a name="to-use-getbuffer-and-releasebuffer-to-access-the-internal-character-buffer-of-a-cstring-object"></a>Использование GetBuffer и ReleaseBuffer для доступа к внутреннему символьному буферу объекта CString  
  
1.  Вызовите `GetBuffer` для объекта `CString` и укажите требуемую длину буфера.  
  
2.  Используйте указатель, возвращенный `GetBuffer`, для записи символов напрямую в объект `CString`.  
  
3.  Вызовите `ReleaseBuffer` для объекта `CString`, чтобы обновить все внутренние сведения о состоянии `CString`, например длину строки. После непосредственного изменения содержимого объекта `CString` необходимо вызвать `ReleaseBuffer` до вызова любых других функций-членов `CString`.  
  
##  <a name="_core_using_cstring_objects_with_variable_argument_functions"></a>Использование объектов CString с функциями аргументов переменных  
 Некоторые функции C принимают переменное число аргументов. Ярким примером этого является `printf_s`. Из-за способа объявления этого вида функции компилятор не может быть уверен в типе аргументов и не может определить, какую операцию преобразования требуется выполнить для каждого аргумента. Таким образом, вам важно использовать явное приведение типа при передаче объекта `CString` в функцию, которая принимает переменное число аргументов.  
  
 Чтобы использовать объект `CString` в функции с переменным числом аргументов, выполните явное приведение `CString` к строке `LPCTSTR`, как показано в следующем примере.  
  
 [!code-cpp[NVC_ATLMFC_Utilities#190](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_2.cpp)]  
  
##  <a name="_core_specifying_cstring_formal_parameters"></a>Указание формальных параметров CString  
 Для большинства функций, которым требуется строковый аргумент, в прототипе функции в качестве указателя `const` на символ (`LPCTSTR`) вместо `CString` лучше всего указать формальный параметр. При задании формального параметра в качестве указателя `const` на символ вы можете передать указатель в массив `TCHAR`, строковый литерал [`"hi there"`] либо объект `CString`. Объект `CString` автоматически преобразуется в `LPCTSTR`. В любом месте, где можно использовать `LPCTSTR`, также можно воспользоваться и объектом `CString`.  
  
 Можно также указать формальный параметр как ссылки на константную строку (то есть, `const CString&`), если аргумент не будет изменен. Удалите модификатор `const`, если строка будет изменена функцией. Если требуется использовать по умолчанию значение NULL, инициализируйте его с нулевой строкой [`""`], как показано ниже:  
  
 [!code-cpp[NVC_ATLMFC_Utilities#191](../atl-mfc-shared/codesnippet/cpp/cstring-operations-relating-to-c-style-strings_3.cpp)]  
  
 Для большинства результатов функции вы можете просто возвратить объект `CString` по значению.  
  
## <a name="see-also"></a>См. также  
 [Строки (ATL и MFC)](../atl-mfc-shared/strings-atl-mfc.md)   
 [Передача аргументов CString](../atl-mfc-shared/cstring-argument-passing.md)

