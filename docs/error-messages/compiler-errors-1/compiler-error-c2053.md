---
title: "Ошибка компилятора C2053 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2053
dev_langs: C++
helpviewer_keywords: C2053
ms.assetid: 13324c85-13a8-4996-bd42-a31bfe7ff80f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1790a1b99493f4b10cc3193f11e63af6901a8d2c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c2053"></a>Ошибка компилятора C2053
«Идентификатор»: несоответствие двухбайтовых строк  
  
 Расширенная строка назначается несовместимый тип.  
  
 Следующий пример приводит к возникновению ошибки C2053:  
  
```  
// C2053.c  
int main() {  
   char array[] = L"Rika";   // C2053  
}  
```