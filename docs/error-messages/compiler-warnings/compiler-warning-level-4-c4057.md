---
title: Предупреждение компилятора (уровень 4) C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 234223ee7b6a031dd9e2c0fc88ccbbdba05beb3c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401440"
---
# <a name="compiler-warning-level-4-c4057"></a>Предупреждение компилятора (уровень 4) C4057

"оператор": "идентификатор1" отличается от "идентификатор2" по косвенному обращению к слегка разным базовым типам

Два выражения указателя ссылаются на разные базовые типы. Выражения используются без преобразования.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Сочетание типов со знаком и без знака.

1. Сочетание **коротких** и **длинных** типов.