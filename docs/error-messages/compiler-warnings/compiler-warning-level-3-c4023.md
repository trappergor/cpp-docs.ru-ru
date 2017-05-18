---
title: "Предупреждение (уровень 3) C4023 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4023
dev_langs:
- C++
helpviewer_keywords:
- C4023
ms.assetid: 615d5374-d7c1-42eb-acfd-917c053270c8
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 420dc18e62a4b40124ef49171c2c76a66ed0cb64
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-3-c4023"></a>Предупреждение компилятора (уровень 3) C4023
"символ": относительный указатель передан в функцию без прототипа: номер параметра  
  
 Передача относительного указателя в функцию без прототипа нормализует указатель с непредвиденными результатами.  
  
 Чтобы устранить это предупреждение, используйте функции прототипа, которые передаются относительными указателями.
