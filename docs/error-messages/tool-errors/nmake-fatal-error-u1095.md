---
title: Неустранимая ошибка NMAKE U1095 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- U1095
dev_langs:
- C++
helpviewer_keywords:
- U1095
ms.assetid: a392582b-06db-4568-9c13-450293a4fbda
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13c819d18149e61bca71f6a4cb10ea851a2d485d
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33317249"
---
# <a name="nmake-fatal-error-u1095"></a>Неустранимая ошибка NMAKE U1095
Командная строка «Командная строка» слишком длинный  
  
 После расширения макроса данной командной строки превышает ограничение на длину командной строки для операционной системы.  
  
 MS-DOS разрешает до 128 символов в командной строке.  
  
 Если для программы, которая может принимать данные из файла в командной строке команду, следует изменить команду и обеспечить ввод из файла на диске или подставляемого файла. Например ссылки и LIB принимать входные данные из файла ответов.