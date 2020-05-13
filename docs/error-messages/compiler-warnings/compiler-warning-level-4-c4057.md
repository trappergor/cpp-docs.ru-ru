---
title: Предупреждение компилятора (уровень 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 45d2db56a7b0fc871de60743954012faf0f5c366
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80185390"
---
# <a name="compiler-warning-level-4-c4057"></a>Предупреждение компилятора (уровень 4) C4057

"оператор": "идентификатор1" отличается от "идентификатор2" по косвенному обращению к слегка разным базовым типам

Два выражения указателя ссылаются на разные базовые типы. Выражения используются без преобразования.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Сочетание типов со знаком и без знака.

1. Сочетание **коротких** и **длинных** типов.
