---
title: Ошибка компилятора C2870 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2870
dev_langs:
- C++
helpviewer_keywords:
- C2870
ms.assetid: 80523ee9-1fd3-4dc4-8a77-5083deb99066
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5fe9f47a96422493d6d731a18add8c23ff683f14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33243493"
---
# <a name="compiler-error-c2870"></a>Ошибка компилятора C2870
«Имя»: определение пространства имен должно отображаться либо в области видимости файла, или непосредственно в другом определении пространства имен  
  
 Пространства имен `name` неправильно. Пространства имен должны быть определены в области видимости файла (вне всех блоков и классов) или непосредственно в другом пространстве имен.  
  
 Следующий пример приводит к возникновению ошибки C2870:  
  
```  
// C2870.cpp  
// compile with: /c  
int main() {  
   namespace A { int i; };   // C2870  
}  
```