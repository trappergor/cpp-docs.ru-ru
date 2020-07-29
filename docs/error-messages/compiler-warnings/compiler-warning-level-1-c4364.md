---
title: Предупреждение компилятора (уровень 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 5423a5525f9bef4d949bfee2de058fe19d0ec181
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220045"
---
# <a name="compiler-warning-level-1-c4364"></a>Предупреждение компилятора (уровень 1) C4364

\#используется для сборки "File", которая ранее встречалась в расположении (line_number) без атрибута as_friend; as_friend не применяется

`#using`Директива была повторена для данного файла метаданных, но **`as_friend`** Квалификатор не использовался в первом экземпляре; компилятор будет игнорировать второй **`as_friend`** .

Дополнительные сведения см. в разделе [дружественные сборки (C++)](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Пример

В приведенном ниже примере создается компонент.

```cpp
// C4364.cpp
// compile with: /clr /LD
ref class A {};
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4364.

```cpp
// C4364_b.cpp
// compile with: /clr /W1 /c
#using " C4364.dll"
#using " C4364.dll" as_friend   // C4364
```
