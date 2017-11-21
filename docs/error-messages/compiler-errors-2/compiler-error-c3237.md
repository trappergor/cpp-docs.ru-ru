---
title: "Ошибка компилятора C3237 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C3237
dev_langs: C++
helpviewer_keywords: C3237
ms.assetid: 690970c8-e13b-4ff3-96e3-5fd93c4d356b
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 21642184acebf358e92802f0a1aad9e2d227110a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3237"></a>Ошибка компилятора C3237
"универсальный_класс": универсальный класс не может быть пользовательским атрибутом  
  
 Универсальные классы не могут быть пользовательскими атрибутами.  
  
## <a name="example"></a>Пример  
 При компиляции следующего примера возникнет ошибка C3237.  
  
```  
// C3237.cpp  
// compile with: /clr /c  
// C3237 expected  
using namespace System;  
  
generic <class T>  
// Delete the following line to resolve.  
[attribute(AttributeTargets::All, AllowMultiple=true)]  
public ref class GR {};  
```