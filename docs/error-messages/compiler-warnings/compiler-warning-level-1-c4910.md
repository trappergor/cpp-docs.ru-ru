---
title: Предупреждение компилятора (уровень 1) C4910
ms.date: 11/04/2016
f1_keywords:
- C4910
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: b17df9d7a9997e5d8ef37a4721de8693968cbbdf
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214455"
---
# <a name="compiler-warning-level-1-c4910"></a>Предупреждение компилятора (уровень 1) C4910

" \<identifier> ": "__declspec (dllexport)" и "extern" несовместимы при явном создании экземпляра

Явный экземпляр шаблона с именем *\<identifier>* изменяется как с помощью `__declspec(dllexport)` ключевых слов, так и **`extern`** . Однако эти ключевые слова являются взаимоисключающими. `__declspec(dllexport)`Ключевое слово означает создание экземпляра класса шаблона, а **`extern`** ключевое слово означает, что не создавать экземпляр класса шаблона автоматически.

## <a name="see-also"></a>См. также раздел

[Явное создание экземпляра](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Общие правила и ограничения](../../cpp/general-rules-and-limitations.md)
