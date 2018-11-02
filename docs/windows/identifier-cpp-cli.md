---
title: __identifier (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
ms.openlocfilehash: b63b7f6fe83c7761846d1d0c70de8b1665ad2f22
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50641042"
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)

Позволяет использовать ключевые слова C++ в качестве идентификаторов.

## <a name="all-platforms"></a>Все платформы

### <a name="syntax"></a>Синтаксис

```cpp
__identifier(C++_keyword)
```

### <a name="remarks"></a>Примечания

Использование **__identifier** ключевое слово для идентификаторов, которые не являются ключевые слова, разрешено, но настоятельно не рекомендуется в рамках стиля.

## <a name="windows-runtime"></a>Среда выполнения Windows

### <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

### <a name="examples"></a>Примеры

**Пример**

В следующем примере класс с именем **шаблона** создается на языке C# и распространяемых в виде библиотеки DLL. В C + +/ CLI программы, которая использует **шаблона** класс, **__identifier** ключевое слово скрывает тот факт, **шаблона** является ключевым словом standard C++.

```cs
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /ZW
#using <identifier_template.dll>
int main() {
   __identifier(template)^ pTemplate = ref new __identifier(template)();
   pTemplate->Run();
}
```

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

**__Identifier** ключевое слово может использоваться с `/clr` параметр компилятора.

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере класс с именем **шаблона** создается на языке C# и распространяемых в виде библиотеки DLL. В C + +/ CLI программы, которая использует **шаблона** класс, **__identifier** ключевое слово скрывает тот факт, **шаблона** является ключевым словом standard C++.

```cs
// identifier_template.cs
// compile with: /target:library
public class template {
   public void Run() { }
}
```

```cpp
// keyword__identifier.cpp
// compile with: /clr
#using <identifier_template.dll>

int main() {
   __identifier(template) ^pTemplate = gcnew __identifier(template)();
   pTemplate->Run();
}
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>
[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)