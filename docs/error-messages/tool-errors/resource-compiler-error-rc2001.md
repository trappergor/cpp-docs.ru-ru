---
title: Ошибка компилятора ресурсов RC2001 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- RC2001
dev_langs:
- C++
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 0ef1fd5d29fc5784ee418a8456cacec37e943b73
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33322423"
---
# <a name="resource-compiler-error-rc2001"></a>Ошибка компилятора ресурсов RC2001
символ новой строки в константе  
  
 Строковая константа была продолжена на второй строке отсутствует либо обратную косую черту (**\\**) или закрытия и открытия двойные кавычки (**»**).  
  
 Чтобы приостановить выполнение строковая константа, на две строки в исходном файле, выполните одно из следующих:  
  
-   Завершите первую строку символом продолжения строки обратную косую черту.  
  
-   Строки в первой строке с двойной кавычкой закройте и откройте строку на следующую строку с еще один символ кавычек.  
  
 Первая строка escape-последовательность для внедрения символа новой строки в строковую константу "\n" недостаточно.