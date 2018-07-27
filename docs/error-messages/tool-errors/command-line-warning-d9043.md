---
title: Предупреждение командной строки D9043 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- D9043
dev_langs:
- C++
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65bf672418b49dbf6017374ab7cd18caa61d7403
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33294753"
---
# <a name="command-line-warning-d9043"></a>Предупреждение командной строки D9043
Недопустимое значение «порог_предупреждения» для параметра «параметр_компилятора»; предполагается "4999"; Предупреждения анализа кода не связаны с уровнями предупреждений  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C9043.  
  
```  
// D9043.cpp  
// compile with: /analyze /w16001  
// D9043 warning expected  
int main() {}  
```