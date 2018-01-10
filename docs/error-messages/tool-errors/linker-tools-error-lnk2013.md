---
title: "Ошибка средств компоновщика LNK2013 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2013
dev_langs: C++
helpviewer_keywords: LNK2013
ms.assetid: 21408e2d-3f56-4d1f-a031-00df70785ed4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8cf88f768f05eee06ae8ffaa66f8de5a9c443f82
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2013"></a>Ошибка средств компоновщика LNK2013
Переполнение адресной привязки тип адресной привязки. Целевой «имя символа» лежит вне допустимого диапазона  
  
 Компоновщик не может поместиться необходимые адрес или смещение в данной инструкции, так как конечный символ находится слишком далеко от расположения инструкции.  
  
 Можно разрешить эту проблему, создав несколько изображений или с помощью [/ORDER](../../build/reference/order-put-functions-in-order.md) параметр, чтобы инструкция и целевое расположены ближе друг с другом.  
  
 Если имя символа определяемого пользователем символа (и не компилятором символа), попробуйте следующие действия для устранения этой ошибки:  
  
-   Измените статическую функцию, чтобы быть статическим.  
  
-   Переименуйте раздел кода, содержащий статическую функцию, чтобы быть таким же, как вызывающий объект.  
  
 Используйте `DUMPBIN /SYMBOLS`, чтобы увидеть, если функция является статическим.