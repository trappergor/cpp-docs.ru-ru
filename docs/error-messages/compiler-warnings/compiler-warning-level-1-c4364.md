---
title: Предупреждение компилятора (уровень 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 79c8809b4de9d6853aaacec4283bf01d0e89305e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80187106"
---
# <a name="compiler-warning-level-1-c4364"></a>Предупреждение компилятора (уровень 1) C4364

\#, используемое для сборки "File", ранее встречалось в расположении (line_number) без атрибута as_friend; as_friend не применяется

Директива `#using` была повторена для данного файла метаданных, но квалификатор `as_friend` не использовался в первом экземпляре. компилятор будет игнорировать второй `as_friend`.

Дополнительные сведения см. в разделе [дружественныеC++сборки ()](../../dotnet/friend-assemblies-cpp.md).

## <a name="example"></a>Пример

В следующем примере создается компонент.

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
