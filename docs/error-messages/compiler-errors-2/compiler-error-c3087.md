---
title: Ошибка компилятора C3087 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3087
dev_langs:
- C++
helpviewer_keywords:
- C3087
ms.assetid: 4f5bdd52-a853-4f02-b160-6868e9190b9d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a6e1446d8d062f97e9161e62fae5052580174c83
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33245313"
---
# <a name="compiler-error-c3087"></a>Ошибка компилятора C3087
"именованный_аргумент": вызов атрибута "атрибут" уже инициализирует данный член  
  
 Именованный аргумент был указан в том же блоке атрибута, что и неименованный аргумент для того же значения. Укажите только именованный или неименованный аргумент.  
  
## <a name="example"></a>Пример  
 В следующем примере возникает ошибка C3087:  
  
```  
// C3087.cpp  
// compile with: /c  
[idl_quote("quote1", text="quote2")];   // C3087  
[idl_quote(text="quote3")];   // OK  
[idl_quote("quote4")];   // OK  
```