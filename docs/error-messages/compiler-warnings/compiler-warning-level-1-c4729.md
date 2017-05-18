---
title: "Компилятор C4729 предупреждение (уровень 1) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4729
dev_langs:
- C++
helpviewer_keywords:
- C4729
ms.assetid: 36a0151f-f258-48d9-9444-ae6d41ff70a4
caps.latest.revision: 7
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
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: babe4bf05b93d92584cea952d6b70da008223260
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-1-c4729"></a>Предупреждение компилятора (уровень 1) C4729
слишком большая функция для предупреждений, основанных на оптимизации структуры кода  
  
 Это предупреждение возникает в случае, если функция слишком велика для компиляции с надежной проверкой ситуаций, в которых могут возникать предупреждения. Это предупреждение только в том случае, формируемое, когда [/Od](../../build/reference/od-disable-debug.md) используется параметр компилятора.  
  
 Чтобы устранить это предупреждение, разделите функцию на более мелкие функции.
