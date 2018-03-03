---
title: "Ошибка компилятора C2818 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2818
dev_langs:
- C++
helpviewer_keywords:
- C2818
ms.assetid: 715fc7c9-0c6d-452b-b7f5-1682cea5e907
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f409acd9ba18972ca414c81cbcabd279e8903bcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2818"></a>Ошибка компилятора C2818
Применение перегруженного «operator ->» является рекурсивным через тип «тип»  
  
 Переопределение оператор доступа к членам класса содержится рекурсивный `return` инструкции. Чтобы переопределить `->` оператор, необходимо переместить рекурсивную подпрограмму в отдельную функцию, которая вызывается из оператора переопределить функцию.