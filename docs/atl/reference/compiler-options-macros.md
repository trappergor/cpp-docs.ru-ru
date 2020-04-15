---
title: Варианты компилятора Макрос
ms.date: 08/19/2019
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
ms.openlocfilehash: 702324c3300ff23bb60113529a681e3b8fa99354
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81331624"
---
# <a name="compiler-options-macros"></a>Варианты компилятора Макрос

Эти макросы управляют определенными функциями компилятора.

|||
|-|-|
|[_ATL_ALL_WARNINGS](#_atl_all_warnings)|Символ, позволяющий ошибки в проектах, преобразованных из предыдущих версий ATL.|
|[_ATL_APARTMENT_THREADED](#_atl_apartment_threaded)|Определите, использует ли один или несколько объектов для резьбы по квартире.|
|[_ATL_CSTRING_EXPLICIT_CONSTRUCTORS](#_atl_cstring_explicit_constructors)|Делает `CString` некоторые конструкторы явными, предотвращая любые непреднамеренные преобразования.|
|[_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning)|Определите этот макрос, чтобы использовать стандартный синтаксис, совместимый со стандартом C, который генерирует ошибку компилятора C4867, когда нестандартный синтаксис используется для инициализации указателя на функцию члена.|
|[_ATL_FREE_THREADED](#_atl_free_threaded)|Определите, использует ли один или несколько объектов свободные или нейтральные потоки.|
|[_ATL_MULTI_THREADED](#_atl_multi_threaded)|Символ, указывающий на проект, будет иметь объекты, помеченные как как свободные, так и нейтральные. Вместо этого следует использовать [макрос-_ATL_FREE_THREADED.](#_atl_free_threaded)|
|[_ATL_NO_AUTOMATIC_NAMESPACE](#_atl_no_automatic_namespace)|Символ, предотвращая использование пространства имен по умолчанию в качестве ATL.|
|[_ATL_NO_COM_SUPPORT](#_atl_no_com_support)|Символ, препятствующие комборному коду, компоновку, компиляции с помощью проекта.|
|[ATL_NO_VTABLE](#atl_no_vtable)|Символ, предотвращая инициализируемую в конструкторе и деструктиве класса указателя vtable.|
|[ATL_NOINLINE](#atl_noinline)|Символ, указывающий на функцию, не должен быть встроен.|
|[_ATL_SINGLE_THREADED](#_atl_single_threaded)|Определите, используют ли все объекты одну модель потоков.|

## <a name="_atl_all_warnings"></a><a name="_atl_all_warnings"></a>_ATL_ALL_WARNINGS

Символ, позволяющий ошибки в проектах, преобразованных из предыдущих версий ATL.

```
#define _ATL_ALL_WARNINGS
```

### <a name="remarks"></a>Remarks

Перед visual C .NET 2002 ATL отключил множество предупреждений и оставил их отключенными, чтобы они никогда не появлялись в пользовательском коде. В частности:

- Условное выражение C4127 является постоянным

- C4786 'идентификатор' : идентификатор был усечен до "числа" символов в информации об отладке

- C4201 нестандартное расширение используется: безымянный struct/union

- C4103 'filename' : используется #pragma пакет для изменения выравнивания

- C4291 'декларация' : не найдено соответствующего оператора удаления; память не будет освобождена, если инициализация бросает исключение

- C4268 'идентификатор' : 'const' статические /глобальные данные инициализированы с генератором компилятора по умолчанию заполняет объект с нулями

- C4702 недосягаемый код

В проектах, преобразованных из предыдущих версий, эти предупреждения по-прежнему отключены заголовками библиотек.

Добавив следующую строку в *файл pch.h* *(stdafx.h* в Visual Studio 2017 и ранее) перед включением заголовков библиотек, такое поведение может быть изменено.

[!code-cpp[NVC_ATL_Utilities#97](../../atl/codesnippet/cpp/compiler-options-macros_1.h)]

Если `#define` это добавляется, заголовки ATL тщательно сохраняют состояние этих предупреждений, чтобы они не были отключены глобально (или если пользователь явно отключает индивидуальные предупреждения, а не для их включения).

Новые проекты имеют этот `#define` набор в *pch.h* *(stdafx.h* в Visual Studio 2017 и ранее) по умолчанию.

## <a name="_atl_apartment_threaded"></a><a name="_atl_apartment_threaded"></a>_ATL_APARTMENT_THREADED

Определите, использует ли один или несколько объектов для резьбы по квартире.

```
_ATL_APARTMENT_THREADED
```

### <a name="remarks"></a>Remarks

Определяет квартиру резьбы. [См. Определение модели потока проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других параметров потоков и [опций, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) для описания моделей потоков, доступных для объекта ATL.

## <a name="_atl_cstring_explicit_constructors"></a><a name="_atl_cstring_explicit_constructors"></a>_ATL_CSTRING_EXPLICIT_CONSTRUCTORS

Делает `CString` некоторые конструкторы явными, предотвращая любые непреднамеренные преобразования.

```
_ATL_CSTRING_EXPLICIT_CONSTRUCTORS
```

### <a name="remarks"></a>Remarks

Когда этот конструктор определен, все конструкторы CString, которые принимают один параметр, компилируются с явным ключевым словом, что предотвращает неявные преобразования аргументов ввода. Это означает, например, что при определении _UNICODE, если вы попытаетесь использовать строку char' в качестве аргумента конструктора CString, то возникает ошибка компилятора. Используйте этот макрос в ситуациях, когда вам нужно предотвратить неявные преобразования между узкими и широкими типами строк.

Используя _T макрос на всех аргументах строки конструктора, можно определить _ATL_CSTRING_EXPLICIT_CONSTRUCTORS и избежать ошибок компиляции независимо от того, определяется ли _UNICODE.

## <a name="_atl_enable_ptm_warning"></a><a name="_atl_enable_ptm_warning"></a>_ATL_ENABLE_PTM_WARNING

Определите этот макрос, чтобы заставить использовать синтаксис, совместимый со стандартом ANSI C', для указателя на функции членов. Использование этого макроса приведет к тому, что ошибка компилятора C4867 будет сгенерирована, когда нестандартный синтаксис используется для инициализации указателя на функцию члена.

```
#define _ATL_ENABLE_PTM_WARNING
```

### <a name="remarks"></a>Remarks

Библиотеки ATL и MFC были изменены в соответствии с улучшенным стандартным соответствием компилятора Microsoft C'. Согласно стандарту ANSI C е, синтаксис указателя на функцию `&CMyClass::MyFunc`члена класса должен быть .

Когда [_ATL_ENABLE_PTM_WARNING](#_atl_enable_ptm_warning) не определен (дело по умолчанию), ATL/MFC отражает ошибку C4867 на макрокартах (в частности, карты сообщений), так что код, созданный в более ранних версиях, может продолжать строиться по-прежнему. Если вы определяете **_ATL_ENABLE_PTM_WARNING,** ваш код должен соответствовать стандарту СЗ.

Однако нестандартная форма была унипрачена. Необходимо перевести существующий код в стандартный синтаксис, соответствующий требованиям СЗ. Например, приведенный ниже код

[!code-cpp[NVC_MFCListView#14](../../atl/reference/codesnippet/cpp/compiler-options-macros_2.cpp)]

следует изменить на

[!code-cpp[NVC_MFCListView#11](../../atl/reference/codesnippet/cpp/compiler-options-macros_3.cpp)]

Для макросов карты добавьте символ амперсанда «&». Вы не должны добавлять символ снова в свой код.

## <a name="_atl_free_threaded"></a><a name="_atl_free_threaded"></a>_ATL_FREE_THREADED

Определите, использует ли один или несколько объектов свободные или нейтральные потоки.

```
_ATL_FREE_THREADED
```

### <a name="remarks"></a>Remarks

Определяет бесплатное резьбовое. Бесплатная резьба эквивалентна многопоточной модели апартаментов. [См. Определение модели потока проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других параметров потоков и [опций, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) для описания моделей потоков, доступных для объекта ATL.

## <a name="_atl_multi_threaded"></a><a name="_atl_multi_threaded"></a>_ATL_MULTI_THREADED

Символ, указывающий на проект, будет иметь объекты, помеченные как как свободные, так и нейтральные.

```
_ATL_MULTI_THREADED
```

### <a name="remarks"></a>Remarks

Если этот символ определен, ATL будет втягивать код, который будет правильно синхронизировать доступ к глобальным данным. Вместо нового кода следует использовать эквивалентный [макрос-_ATL_FREE_THREADED.](#_atl_free_threaded)

## <a name="_atl_no_automatic_namespace"></a><a name="_atl_no_automatic_namespace"></a>_ATL_NO_AUTOMATIC_NAMESPACE

Символ, предотвращая использование пространства имен по умолчанию в качестве ATL.

```
_ATL_NO_AUTOMATIC_NAMESPACE
```

### <a name="remarks"></a>Remarks

Если этот символ не определен, в том числе atlbase.h будет **выполняться с помощью пространства имен ATL** по умолчанию, что может привести к конфликтам именования. Чтобы предотвратить это, определите этот символ.

## <a name="_atl_no_com_support"></a><a name="_atl_no_com_support"></a>_ATL_NO_COM_SUPPORT

Символ, препятствующие комборному коду, компоновку, компиляции с помощью проекта.

```
_ATL_NO_COM_SUPPORT
```

## <a name="atl_no_vtable"></a><a name="atl_no_vtable"></a>ATL_NO_VTABLE

Символ, предотвращая инициализируемую в конструкторе и деструктиве класса указателя vtable.

```
ATL_NO_VTABLE
```

### <a name="remarks"></a>Remarks

Если указатель vtable предотвращается от инициализации в конструкторе и деструкторе класса, связующий может устранить vtable и все функции, на которые он указывает. Расширяется до **__declspec (novtable)**.

### <a name="example"></a>Пример

[!code-cpp[NVC_ATL_COM#53](../../atl/codesnippet/cpp/compiler-options-macros_4.h)]

## <a name="atl_noinline"></a><a name="atl_noinline"></a>ATL_NOINLINE

Символ, указывающий на функцию, не должен быть встроен.

```
    ATL_NOINLINE inline
    myfunction()
    {
    ...
    }
```

### <a name="parameters"></a>Параметры

*myfunction*<br/>
Функция, которая не должна быть подстроена.

### <a name="remarks"></a>Remarks

Используйте этот символ, если вы хотите, чтобы функция не была включена в состав компилятора, даже если она должна быть объявлена в качестве встроенной, так что она может быть помещена в файл заголовка. Расширяется до **__declspec (noinline)**.

## <a name="_atl_single_threaded"></a><a name="_atl_single_threaded"></a>_ATL_SINGLE_THREADED

Определите, используют ли все объекты одну модель резьбы

```
_ATL_SINGLE_THREADED
```

### <a name="remarks"></a>Remarks

Уточняется, что объект всегда работает в основном потоке COM. [См. Определение модели потока проекта](../../atl/specifying-the-threading-model-for-a-project-atl.md) для других параметров потоков и [опций, ATL Simple Object Wizard](../../atl/reference/options-atl-simple-object-wizard.md) для описания моделей потоков, доступных для объекта ATL.

## <a name="see-also"></a>См. также раздел

[Макросы](../../atl/reference/atl-macros.md)
