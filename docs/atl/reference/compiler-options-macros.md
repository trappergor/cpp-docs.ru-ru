---
title: "Параметры компилятора, макросы | Документы Microsoft"
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
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dbce962873194c1bdcb063537247650cff568e35
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-options-macros"></a>Макросы параметров компилятора
Эти макросы управления функциями определенного компилятора.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Символ, который включает ошибки в проектах, преобразованные из предыдущих версий библиотеки ATL.|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Если один или несколько объектов использовать потоковое определите.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Гарантирует `CString` конструкторы explicit, Предотвращение непреднамеренного преобразования.|  
|[ТАКЖЕ БИБЛИОТЕКАХ](#_atl_enable_ptm_warning)|Определите этот макрос, чтобы использовать стандартные совместимые синтаксиса C++, который создает ошибку компилятора C4867 при использовании нестандартных синтаксиса для инициализации указателя на функцию-член.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Определите, если один или несколько объектов используйте бесплатные или нейтральным потоков.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Символ, указывающий проект будет объектов, помеченных как, бесплатный или нейтральным. Макрос [_ATL_FREE_THREADED](#_atl_free_threaded) следует использовать.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Символ, который предотвращает использование пространства имен по умолчанию как ATL.|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Символ, предотвращающий код, связанный с COM компилируемого проекта.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Символ, который предотвращает инициализацию в конструктор и деструктор класса указателя vtable.|  
|[ATL_NOINLINE](#atl_noinline)|Символ, указывающий функции не может быть встроен.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Определите, если все объекты используют однопотоковую модель.|  
  
##  <a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS  
 Символ, который включает ошибки в проектах, преобразованные из предыдущих версий библиотеки ATL.  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Примечания  
 До Visual C++ .NET 2002 ATL массу предупреждения отключены и они отключены, чтобы никогда не показано в коде пользователя. В частности:  
  
-   Ошибка C4127 условное выражение является константой  
  
-   C4786 «идентификатор»: идентификатор был сокращен до «число» знаков в отладочной информации  
  
-   Использовано нестандартное расширение C4201: безымянные структуры или объединения  
  
-   C4103 «ИмяФайла»: можно изменять выравнивание #pragma pack  
  
-   C4291 «объявление»: не обнаружен; соответствующий оператор delete память не будет освобожден при инициализации возникнет исключение  
  
-   C4268 «идентификатор»: «const» статическое или глобальное данные, инициализированные конструктором по умолчанию, созданные компилятором заполняет объект нулями  
  
-   C4702 недостижимый код  
  
 В проектах, преобразованные из предыдущих версий эти предупреждения отключены по-прежнему заголовков библиотеки.  
  
 Добавив в файл stdafx.h следующую строку перед включением заголовков библиотеки, можно изменить это поведение.  
  
 [!code-cpp[NVC_ATL_Utilities&#97;](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 Если этот `#define` добавляется, заголовки, ATL, осторожность, чтобы сохранить состояние этих предупреждений, чтобы они не отключены глобально (или если пользователь явно отключить отдельные предупреждения, не позволяя им).  
  
 Новые проекты, созданные с помощью Visual C++ .NET 2002 будет `#define` по умолчанию значение в файле stdafx.h.  
  
##  <a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED  
 Если один или несколько объектов использовать потоковое определите.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Примечания  
 Указывает потоковое. В разделе [указание потоковой модели проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других потоков параметры, и [параметров, мастер простых объектов ATL](../../atl/reference/options-atl-simple-object-wizard.md) описание работы с потоками моделей для объекта ATL.  
  
##  <a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 Гарантирует `CString` конструкторы explicit, Предотвращение непреднамеренного преобразования.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Примечания  
 Если оно определено, все CString конструкторы, которые принимают один параметр компилируются с явной ключевое слово, которое запрещает неявные преобразования входных аргументов. Это означает, например, что если определяется _UNICODE, при попытке использовать char * строку в качестве аргумента конструктора CString, приведет к ошибке компилятора. Используйте этот макрос в ситуациях, когда необходимо предотвратить неявные преобразования между узкий и расширенные строковые типы.  
  
 Используя макрос _T все строковые аргументы конструктора, можно определить _ATL_CSTRING_EXPLICIT_CONSTRUCTORS и избежать ошибок компиляции, независимо от того, определен ли _UNICODE.  
  
##  <a name="_atl_enable_ptm_warning"></a>ТАКЖЕ БИБЛИОТЕКАХ  
 Определите этот макрос, чтобы принудительно использовать синтаксис, поддерживающим данный стандарт ANSI C++ для указателей на функции-члены. С помощью этого макроса приведет к ошибке компилятора C4867 создаваться при использовании нестандартных синтаксиса для инициализации указателя на функцию-член.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки ATL и MFC были изменены в соответствии улучшенные C++ соответствие стандарту компилятор Visual C++. Согласно стандарту ANSI C++ синтаксис указателя на функцию-член класса должен быть `&CMyClass::MyFunc`.  
  
 Когда [также библиотеках](#_atl_enable_ptm_warning) не определен (вариант по умолчанию), ATL и MFC отключает ошибка C4867 в сопоставлениях макрос (схемы очередь сообщений), так что код, который был создан в более ранних версиях можно продолжать выполнять построение, как и раньше. Если определить **также библиотеках**, код должен быть совместимым стандарта C++.  
  
 Однако нестандартные формы являются устаревшими, поэтому необходимо переместить существующий код C++ стандартный синтаксис. Например следующий код:  
  
 [!code-cpp[NVC_MFCListView&#14;](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 Должно быть изменено на:  
  
 [!code-cpp[NVC_MFCListView&11;](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 Обратите внимание, что карты макросов, добавьте символ «&», не следует добавлять его снова в коде.  
  
##  <a name="_atl_free_threaded"></a>_ATL_FREE_THREADED  
 Определите, если один или несколько объектов используйте бесплатные или нейтральным потоков.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Примечания  
 Указывает свободной потоковой модели. Бесплатная равнозначна модели многопотокового подразделения. В разделе [указание потоковой модели проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других потоков параметры, и [параметров, мастер простых объектов ATL](../../atl/reference/options-atl-simple-object-wizard.md) описание работы с потоками моделей для объекта ATL.  
  
##  <a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED  
 Символ, указывающий проект будет объектов, помеченных как, бесплатный или нейтральным.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Примечания  
 Если этот символ определен, ATL извлекает код, который будет правильно синхронизировать доступ к глобальным данным. Новый код следует использовать эквивалентные макрос [_ATL_FREE_THREADED](#_atl_free_threaded) вместо.  
  
##  <a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE  
 Символ, который предотвращает использование пространства имен по умолчанию как ATL.  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Примечания  
 Если этот символ не определен, включая atlbase.h выполнит **с использованием имен ATL** по умолчанию, что может привести к конфликтов имен. Чтобы избежать этого, определение этого символа.  
  
##  <a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT  
 Символ, предотвращающий код, связанный с COM компилируемого проекта.  
  
```
_ATL_NO_COM_SUPPORT```  
  
##  <a name="atl_no_vtable"></a>  ATL_NO_VTABLE  
 A symbol that prevents the vtable pointer from being initialized in the class's constructor and destructor.  
  
```
ATL_NO_VTABLE
```  
  
### Remarks  
 If the vtable pointer is prevented from being initialized in the class's constructor and destructor, the linker can eliminate the vtable and all of the functions to which it points. Expands to **__declspec(novtable)**.  
  
### Example  
 [!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]  
  
##  <a name="atl_noinline"></a>  ATL_NOINLINE  
 A symbol that indicates a function should not be inlined.  
  
```
    ATL_NOINLINE inline
    myfunction
 { ... }
```  
  
### Parameters  
 *myfunction*  
 The function that should not be inlined.  
  
### Remarks  
 Use this symbol if you want to ensure a function does not get inlined by the compiler, even though it must be declared as inline so that it can be placed in a header file. Expands to **__declspec(noinline)**.  
  
##  <a name="_atl_single_threaded"></a>  _ATL_SINGLE_THREADED  
 Define if all of your objects use the single threading model  
  
```
_ATL_SINGLE_THREADED
```  
  
### Remarks  
 Specifies that the object always runs in the primary COM thread. See [Specifying the Project's Threading Model](../../atl/specifying-the-threading-model-for-a-project-atl.md) for other threading options, and [Options, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) for a description of the threading models available for an ATL object.  
  
## See Also  
 [Macros](../../atl/reference/atl-macros.md)

