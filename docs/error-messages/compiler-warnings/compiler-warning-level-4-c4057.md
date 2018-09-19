---
title: Предупреждение компилятора (уровень 4) C4057 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4057
dev_langs:
- C++
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b10ce6b67fd24b4b8db01177af0225deab9dba4b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46088011"
---
# <a name="compiler-warning-level-4-c4057"></a>Предупреждение компилятора (уровень 4) C4057

"оператор": "идентификатор1" отличается от "идентификатор2" по косвенному обращению к слегка разным базовым типам

Два выражения указателя ссылаются на разные базовые типы. Выражения используются без преобразования.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.

1. Сочетание типов со знаком и без знака.

1. Сочетание **коротких** и **длинных** типов.