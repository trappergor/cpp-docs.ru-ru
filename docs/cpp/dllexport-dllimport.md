---
title: dllexport, dllimport
ms.date: 11/04/2016
f1_keywords:
- dllimport_cpp
- dllexport_cpp
helpviewer_keywords:
- dllexport __declspec keyword
- __declspec keyword [C++], dllexport
- dllimport __declspec keyword
- __declspec keyword [C++], dllimport
ms.assetid: ff95b645-ef55-4e72-b848-df44657b3208
ms.openlocfilehash: 0a8d90770552b8b9ab9169378289108d91811216
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189459"
---
# <a name="dllexport-dllimport"></a>dllexport, dllimport

**Блок, относящийся только к системам Microsoft**

Атрибуты класса хранения **dllexport** и **DllImport** представляют собой расширения для C и C++ языков, специфичные для Майкрософт. Их можно использовать для экспорта функций, данных и объектов в библиотеку DLL или импорта из такой библиотеки.

## <a name="syntax"></a>Синтаксис

```
   __declspec( dllimport ) declarator
   __declspec( dllexport ) declarator
```

## <a name="remarks"></a>Remarks

Эти атрибуты явно определяют интерфейс DLL для ее клиента, который может быть исполняемым файлом или другой библиотекой DLL. Объявление функций как **dllexport** устраняет необходимость в файле определения модуля (DEF), по крайней мере, по отношению к спецификации экспортированных функций. Атрибут **dllexport** заменяет ключевое слово **__export** .

Если класс отмечен как declspec(dllexport), все специализации шаблонов класса в иерархии классов неявно отмечаются как declspec (dllexport). Это означает, что шаблоны класса создаются явно и члены класса должны быть определены.

**dllexport** функции предоставляет функцию с декорированным именем. Для функций C++ сюда входит видоизменение имени. Для функций C или функций, объявленных с модификатором `extern "C"`, сюда входит зависящее от платформы декорирование, основанное на соглашении о вызовах. Сведения о декорировании имен в C/C++ Code см. в разделе [декорированные имена](../build/reference/decorated-names.md). К экспортированным функциям C и функциям `extern "C"` C++, использующим соглашение о вызовах `__cdecl`, не применяется декорирование имен.

Чтобы экспортировать недекорированное имя, можно установить связь с помощью файла определения модуля (DEF-файла), определяющего недекорированное имя в разделе EXPORTS. Дополнительные сведения см. в разделе [EXPORTS](../build/reference/exports.md). Другим способом экспорта недекорированного имени является использование директивы `#pragma comment(linker, "/export:alias=decorated_name")` в исходном коде.

При объявлении **dllexport** или **DllImport**необходимо использовать [синтаксис расширенных атрибутов](../cpp/declspec.md) и ключевое слово **__declspec** .

## <a name="example"></a>Пример

```cpp
// Example of the dllimport and dllexport class attributes
__declspec( dllimport ) int i;
__declspec( dllexport ) void func();
```

Кроме того, чтобы сделать код более понятным, можно использовать макроопределения:

```cpp
#define DllImport   __declspec( dllimport )
#define DllExport   __declspec( dllexport )

DllExport void func();
DllExport int i = 10;
DllImport int j;
DllExport int n;
```

Дополнительные сведения см. в разделе:

- [Определения и объявления](../cpp/definitions-and-declarations-cpp.md)

- [Определение встроенных функций C++ с помощью dllexport и dllimport](../cpp/defining-inline-cpp-functions-with-dllexport-and-dllimport.md)

- [Общие правила и ограничения](../cpp/general-rules-and-limitations.md)

- [Использование dllimport и dllexport в классах C++](../cpp/using-dllimport-and-dllexport-in-cpp-classes.md)

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также раздел

[__declspec](../cpp/declspec.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
