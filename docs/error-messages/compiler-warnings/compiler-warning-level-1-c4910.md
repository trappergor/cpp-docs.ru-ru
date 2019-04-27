---
title: Предупреждение компилятора (уровень 1) C4910
ms.date: 11/04/2016
helpviewer_keywords:
- C4910
ms.assetid: 67963560-fbca-4ca7-93db-06beaf7055f0
ms.openlocfilehash: 49cbbf3369fc4765d93e67e2dca84a4d975560d7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62242894"
---
# <a name="compiler-warning-level-1-c4910"></a>Предупреждение компилятора (уровень 1) C4910

"\<идентификатор >": «__declspec(dllexport)» и «extern» несовместимы при явном создании экземпляра

Явное создание экземпляра шаблона с именем  *\<идентификатор >* изменено `__declspec(dllexport)` и `extern` ключевые слова. Однако эти ключевые слова являются взаимоисключающими. Ключевое слово `__declspec(dllexport)` означает создание экземпляра класса шаблона, тогда как ключевое слово `extern` не разрешает автоматическое создание экземпляра класса шаблона.

## <a name="see-also"></a>См. также

[Явное создание экземпляра](../../cpp/explicit-instantiation.md)<br/>
[dllexport, dllimport](../../cpp/dllexport-dllimport.md)<br/>
[Общие правила и ограничения](../../cpp/general-rules-and-limitations.md)