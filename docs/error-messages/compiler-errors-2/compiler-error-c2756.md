---
title: Ошибка компилятора C2756 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2756
dev_langs:
- C++
helpviewer_keywords:
- C2756
ms.assetid: 42eb988d-4043-4dee-8fd4-596949f69a55
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a3eb61cd111166867be0439709a8b73dd4056099
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33231781"
---
# <a name="compiler-error-c2756"></a>Ошибка компилятора C2756
"тип шаблона": применение аргументов шаблона по умолчанию в частичной специализации не разрешается  
  
 Шаблон для частичной специализации не может содержать аргумент по умолчанию.  
  
 В следующем примере показано возникновение ошибки C2756 и приводятся сведения по ее устранению.  
  
```  
// C2756.cpp  
template <class T>  
struct S {};  
  
template <class T=int>  
// try the following line instead  
// template <class T>  
struct S<T*> {};   // C2756  
```