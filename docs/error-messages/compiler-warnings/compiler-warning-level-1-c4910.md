---
title: Предупреждение компилятора (уровень 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: a3f29cb895da8c06ed43dd5c9956426f3f6014f1
ms.sourcegitcommit: 8762a3f9b5476b4dee03f0ee8064ea606550986e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/04/2019
ms.locfileid: "74810713"
---
# <a name="compiler-warning-level-1-c4910"></a>Предупреждение компилятора (уровень 1) C4910

"\<identifier >": "__declspec (dllexport)" и "extern" несовместимы при явном создании экземпляра

Явное создание экземпляра шаблона с именем *\<identifier >* изменяется как ключевыми словами `__declspec(dllexport)`, так и `extern`. Однако эти ключевые слова являются взаимоисключающими. Ключевое слово `__declspec(dllexport)` означает создание экземпляра класса шаблона, тогда как ключевое слово `extern` не разрешает автоматическое создание экземпляра класса шаблона.

## <a name="see-also"></a>См. также:

[Явное создание экземпляра](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Общие правила и ограничения](../../cpp/general-rules-and-limitations.md)