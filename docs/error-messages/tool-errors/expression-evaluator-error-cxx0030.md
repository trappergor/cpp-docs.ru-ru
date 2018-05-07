---
title: Ошибка вычислителя выражений CXX0030 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- CXX0030
dev_langs:
- C++
helpviewer_keywords:
- CAN0030
- CXX0030
ms.assetid: ada8b48c-09c8-49bf-ae23-313ed663c4fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 669c585c637129c1fb6a480d91b31e5a1264fd22
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="expression-evaluator-error-cxx0030"></a>Ошибка вычислителя выражений CXX0030
невычислимое выражение  
  
 Вычислитель выражений отладчика не удалось получить значение для выражения, по мере записи. Возможной причиной является то, что выражение относится к памяти, находящейся вне адресного пространства программы (разыменования указателя null является одним из примеров). Windows не разрешает доступ к памяти за пределами адресном пространстве программы.  
  
 Может потребоваться переписать выражение с помощью скобок для управления порядком вычисления.  
  
 Эта ошибка идентична ошибке CAN0030.