---
title: "Предупреждение (уровень 2) C4099 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4099
dev_langs: C++
helpviewer_keywords: C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: af0f7aacb5e4600b48120576135b2052af2a5315
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4099"></a>Предупреждение компилятора (уровень 2) C4099
«Идентификатор»: имя типа, ранее отображенное с помощью objecttype1 теперь отображено с помощью «objecttype2»  
  
 Объект, объявленный как структура определен как класс или объекта, объявленного как класс определен как структура. Компилятор использует тип, указанный в определении.  
  
## <a name="example"></a>Пример  
 Следующий пример приводит к возникновению ошибки C4099.  
  
```  
// C4099.cpp  
// compile with: /W2 /c  
struct A;  
class A {};   // C4099, use different identifer or use same object type  
```