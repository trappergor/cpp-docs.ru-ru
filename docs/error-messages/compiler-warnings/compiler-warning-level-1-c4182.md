---
title: "Предупреждение (уровень 1) C4182 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4182
dev_langs: C++
helpviewer_keywords: C4182
ms.assetid: 8970f3c6-e2dd-407e-b2ec-964360eb8b43
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: dfd94e5c98e1ca6e19e3e34c3028c93148871cf4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4182"></a>Предупреждение компилятора (уровень 1) C4182
\#включает уровень вложенности составляет «число»; возможна бесконечная рекурсия  
  
 Компилятору недостаточно места в куче из-за количества вложенных файлов include. Файл include является вложенным, когда он включается из другого файла include.  
  
 Это сообщение является информационным и предшествует ошибке [C1076](../../error-messages/compiler-errors-1/fatal-error-c1076.md).