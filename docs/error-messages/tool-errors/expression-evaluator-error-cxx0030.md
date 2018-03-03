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
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cb120103714c3711fb059fa736398458209b52a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0030"></a>Ошибка вычислителя выражений CXX0030
невычислимое выражение  
  
 Вычислитель выражений отладчика не удалось получить значение для выражения, по мере записи. Возможной причиной является то, что выражение относится к памяти, находящейся вне адресного пространства программы (разыменования указателя null является одним из примеров). Windows не разрешает доступ к памяти за пределами адресном пространстве программы.  
  
 Может потребоваться переписать выражение с помощью скобок для управления порядком вычисления.  
  
 Эта ошибка идентична ошибке CAN0030.