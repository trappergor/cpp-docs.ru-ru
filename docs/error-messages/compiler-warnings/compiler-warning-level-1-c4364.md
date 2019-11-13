---
title: Предупреждение компилятора (уровень 1) C4364
ms.date: 11/04/2016
f1_keywords:
- C4364
helpviewer_keywords:
- C4364
ms.assetid: 1477634c-d60f-4570-ad16-1aaeae24ac7f
ms.openlocfilehash: 716f440cddc3889ec719ef3b295a0d076175be93
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966520"
---
# <a name="compiler-warning-level-1-c4364"></a>Предупреждение компилятора (уровень 1) C4364

\#, используемое для сборки "File", ранее встречалось в расположении (line_number) без атрибута as_friend; as_friend не применяется

Директива `#using` была повторена для данного файла метаданных, но квалификатор `as_friend` не использовался в первом экземпляре. компилятор будет игнорировать второй `as_friend`.

Дополнительные сведения см. в разделе [дружественныеC++сборки ()](../../dotnet/friend-assemblies-cpp.md).

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