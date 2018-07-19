---
title: Предупреждение (уровень 4) C4057 компилятора | Документы Microsoft
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
ms.openlocfilehash: 3217ccb0a96fbe02e152ff82dedeb7e8e54b89ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33292283"
---
# <a name="compiler-warning-level-4-c4057"></a>Предупреждение компилятора (уровень 4) C4057
"оператор": "идентификатор1" отличается от "идентификатор2" по косвенному обращению к слегка разным базовым типам  
  
 Два выражения указателя ссылаются на разные базовые типы. Выражения используются без преобразования.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Чтобы устранить ошибку, проверьте указанные ниже возможные причины ее возникновения.  
  
1.  Сочетание типов со знаком и без знака.  
  
2.  Сочетание **коротких** и **длинных** типов.