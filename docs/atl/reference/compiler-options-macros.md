---
title: Параметры компилятора макросы | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
dev_langs:
- C++
f1_keywords:
- _ATL_ALL_WARNINGS
- _ATL_APARTMENT_THREADED
- '_ATL_CSTRING_EXPLICIT_CONSTRUCTORS '
- _ATL_ENABLE_PTM_WARNING
- _ATL_FREE_THREADED
- _ATL_MULTI_THREADED
- _ATL_NO_AUTOMATIC_NAMESPACE
- _ATL_NO_COM_SUPPORT
- ATL_NO_VTABLE
- ATL_NOINLINE
- _ATL_SINGLE_THREADED
helpviewer_keywords:
- compiler options, macros
ms.assetid: a869adc6-b3de-4299-b040-9ae20b45f82c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1e84c92e8bbf65ff3b8b54111bcce2306628edb1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365857"
---
# <a name="compiler-options-macros"></a>Параметры компилятора, макросы
Эти макросы управления функциями определенного компилятора.  
  
|||  
|-|-|  
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Символ, который включает ошибки в проектах, преобразованные из предыдущих версий библиотеки ATL.|  
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Если один или несколько объектов использовать потоковое определите.|  
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Гарантирует `CString` конструкторы явных, предотвращая любые непреднамеренного преобразования.|  
|[ТАКЖЕ БИБЛИОТЕКАХ](#_atl_enable_ptm_warning)|Определите этот макрос, чтобы использовать C++ Стандартная совместимый синтаксис, который создает ошибку компилятора C4867, если не стандартный синтаксис, используемый для инициализации указателя на функцию-член.|  
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Определите, если один или несколько объектов используйте свободные или нейтральной работа с потоками.|  
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Символ, указывающий проект будет объектов, помеченных как одновременно бесплатный "или" Neutral. Макрос [_ATL_FREE_THREADED](#_atl_free_threaded) следует использовать.|  
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Символ, который предотвращает использование пространства имен по умолчанию как ATL.|  
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Символ, запрещающую COM относящихся к коду, компилируемого с проектом.|  
|[ATL_NO_VTABLE](#atl_no_vtable)|Символ, который предотвращает инициализацию в конструктор и деструктор класса указатель vtable.|  
|[ATL_NOINLINE](#atl_noinline)|Символ, указывающий функцию, не должен быть встроен.|  
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Определите, если все объекты используют один потоковую модель.|  
  
##  <a name="_atl_all_warnings"></a>  _ATL_ALL_WARNINGS  
 Символ, который включает ошибки в проектах, преобразованные из предыдущих версий библиотеки ATL.  
  
```
#define _ATL_ALL_WARNINGS
```  
  
### <a name="remarks"></a>Примечания  
 До Visual C++ .NET 2002 ATL отключены много предупреждений и они отключены, чтобы они никогда не появляются в пользовательском коде. В частности:  
  
-   C4127 условное выражение является константой  
  
-   C4786 «идентификатор»: идентификатор усечен до «число» знаков в сведениях отладки  
  
-   Использовано нестандартное расширение C4201: безымянные структуры или объединения  
  
-   C4103 «имя_файла»: используется для изменения выравнивания #pragma pack  
  
-   C4291 «объявление»: не обнаружен; соответствующий оператор delete память не будут освобождены при инициализации возникнет исключение  
  
-   C4268 «идентификатор»: «const» глобальные и статические данные, инициализированные конструктором по умолчанию, создаваемый компилятором заполняет объект нулями  
  
-   Недостижимый код C4702  
  
 В проектах, преобразованные из предыдущих версий эти предупреждения отключены по-прежнему заголовками библиотек.  
  
 Это поведение можно изменить, добавив следующую строку в файл stdafx.h перед включением заголовков библиотек.  
  
 [!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]  
  
 Если этот `#define` добавляется, заголовков ATL. осторожность, чтобы сохранить состояние этих предупреждений, чтобы они не отключены глобально (или если пользователь явно отключает отдельные предупреждения, не позволяя им).  
  
 Новые проекты имеют это `#define` по умолчанию значение в файле stdafx.h.  
  
##  <a name="_atl_apartment_threaded"></a>  _ATL_APARTMENT_THREADED  
 Если один или несколько объектов использовать потоковое определите.  
  
```
_ATL_APARTMENT_THREADED
```  
  
### <a name="remarks"></a>Примечания  
 Указывает потоковое. В разделе [указание потоковой модели проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других потоков "Параметры", и [параметры, мастер простых объектов ATL](../../atl/reference/options-atl-simple-object-wizard.md) моделей для объекта ATL описание работы с потоками.  
  
##  <a name="_atl_cstring_explicit_constructors"></a>  _ATL_CSTRING_EXPLICIT_CONSTRUCTORS  
 Гарантирует `CString` конструкторы явных, предотвращая любые непреднамеренного преобразования.  
  
```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```  
  
### <a name="remarks"></a>Примечания  
 Если определен, все конструкторы CString, которые принимают один параметр компилируются с явно указанным ключевым словом, не допускает неявные преобразования входных аргументов. Это означает, например, что при определении _UNICODE при попытке использования типа char * строку в качестве аргумента конструктора CString, приведет к ошибке компилятора. Этот макрос используется в ситуациях, где вам необходимо запретить неявное преобразование между обычных, так и расширенные строковые типы.  
  
 С помощью макрос _T на все строковые аргументы конструктора, можно определить _ATL_CSTRING_EXPLICIT_CONSTRUCTORS и избежать ошибок компиляции, независимо от того, определен ли _UNICODE.  
  
##  <a name="_atl_enable_ptm_warning"></a>  ТАКЖЕ БИБЛИОТЕКАХ  
 Чтобы принудительно использовать синтаксис совместимый стандарт ANSI C++ для указателей на функции-члены определите этот макрос. С помощью этого макроса вызовет ошибку компилятора C4867 стеком нестандартный синтаксис, используемый для инициализации указателя на функцию-член.  
  
```
#define _ATL_ENABLE_PTM_WARNING
```  
  
### <a name="remarks"></a>Примечания  
 Библиотеки ATL и MFC были изменены для сопоставления улучшенные C++ соответствие стандартам компилятора Visual C++. Согласно стандарту ANSI C++, синтаксис указателя на функцию-член класса должен быть `&CMyClass::MyFunc`.  
  
 Когда [также библиотеках](#_atl_enable_ptm_warning) не определено (по умолчанию в случае), ATL и MFC отключает ошибка C4867 в maps макрос (схемы очередь сообщений), чтобы код, который был создан в более ранних версиях можно продолжать выполнять построение как раньше. Если определить **также библиотеках**, код должен быть соответствует стандарту C++.  
  
 Тем не менее нестандартные формы являются устаревшими, поэтому необходимо переместить существующего кода C++ стандартный синтаксис. Например следующий код:  
  
 [!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]  
  
 Должно быть изменено на:  
  
 [!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]  
  
 Обратите внимание, что карты макросов, добавьте символ «&», не следует добавлять его снова в коде.  
  
##  <a name="_atl_free_threaded"></a>  _ATL_FREE_THREADED  
 Определите, если один или несколько объектов используйте свободные или нейтральной работа с потоками.  
  
```
_ATL_FREE_THREADED
```  
  
### <a name="remarks"></a>Примечания  
 Указывает свободной потоковой модели. Свободной потоковой модели соответствует модели многопотокового подразделения. В разделе [указание потоковой модели проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других потоков "Параметры", и [параметры, мастер простых объектов ATL](../../atl/reference/options-atl-simple-object-wizard.md) моделей для объекта ATL описание работы с потоками.  
  
##  <a name="_atl_multi_threaded"></a>  _ATL_MULTI_THREADED  
 Символ, указывающий проект будет объектов, помеченных как одновременно бесплатный "или" Neutral.  
  
```
_ATL_MULTI_THREADED
```  
  
### <a name="remarks"></a>Примечания  
 Если этот символ определен, ATL будет получать в коде, который будет правильно синхронизировать доступ к глобальным данным. Новый код должен использовать эквивалентные макрос [_ATL_FREE_THREADED](#_atl_free_threaded) вместо него.  
  
##  <a name="_atl_no_automatic_namespace"></a>  _ATL_NO_AUTOMATIC_NAMESPACE  
 Символ, который предотвращает использование пространства имен по умолчанию как ATL.  
  
```
_ATL_NO_AUTOMATIC_NAMESPACE
```  
  
### <a name="remarks"></a>Примечания  
 Если этот символ не определен, включая atlbase.h выполнит **с использованием пространства имен ATL** по умолчанию, что может привести к конфликты имен. Чтобы избежать этого, определите этот символ.  
  
##  <a name="_atl_no_com_support"></a>  _ATL_NO_COM_SUPPORT  
 Символ, запрещающую COM относящихся к коду, компилируемого с проектом.  
  
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
