---
title: Неустранимая ошибка NMAKE U1095 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- U1095
dev_langs:
- C++
helpviewer_keywords:
- U1095
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 81d93635c50b304a5a2df027691470093d23bdbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-fatal-error-u1095"></a>Неустранимая ошибка NMAKE U1095
Командная строка «Командная строка» слишком длинный  
  
 После расширения макроса данной командной строки превышает ограничение на длину командной строки для операционной системы.  
  
 MS-DOS разрешает до 128 символов в командной строке.  
  
 Если для программы, которая может принимать данные из файла в командной строке команду, следует изменить команду и обеспечить ввод из файла на диске или подставляемого файла. Например ссылки и LIB принимать входные данные из файла ответов.