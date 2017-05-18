---
title: "Ошибка вычислителя выражений CXX0030 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 4a4e82e51943db988805f1ba76495218e8188d2e
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="expression-evaluator-error-cxx0030"></a>Ошибка вычислителя выражений CXX0030
невычислимое выражение  
  
 Вычислитель выражений отладчика не удалось получить значение для выражения, как написано. Возможной причиной является то, что выражение относится к памяти, находящейся вне адресного пространства программы (разыменования указателя null является одним из примеров). Windows не разрешает доступ к областям памяти вне адресного пространства программы.  
  
 Может потребоваться переписать выражение с использованием скобок для управления порядком вычисления.  
  
 Эта ошибка идентична ошибке CAN0030.
