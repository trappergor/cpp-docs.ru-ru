---
title: "Ошибка компилятора ресурсов RC2001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2001
dev_langs: C++
helpviewer_keywords: RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 23b853db3cbea89bf9cb1ba43607c312e5264394
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-error-rc2001"></a>Ошибка компилятора ресурсов RC2001
символ новой строки в константе  
  
 Строковая константа была продолжена на второй строке отсутствует либо обратную косую черту (**\\**) или закрытия и открытия двойные кавычки (**»**).  
  
 Чтобы приостановить выполнение строковая константа, на две строки в исходном файле, выполните одно из следующих:  
  
-   Завершите первую строку символом продолжения строки обратную косую черту.  
  
-   Строки в первой строке с двойной кавычкой закройте и откройте строку на следующую строку с еще один символ кавычек.  
  
 Первая строка escape-последовательность для внедрения символа новой строки в строковую константу "\n" недостаточно.