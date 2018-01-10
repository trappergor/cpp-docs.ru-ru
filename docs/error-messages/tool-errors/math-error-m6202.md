---
title: "Математическая ошибка M6202 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: M6202
dev_langs: C++
helpviewer_keywords: M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 70a9496a2466ee36fed6d9c16194eef3516147f2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6202"></a>Математическая ошибка M6202
«функция»: ошибка _Однотрубный  
  
 Аргумент для данной функции является значением сингулярности для этой функции. Функция не определена для этого аргумента.  
  
 Эта ошибка вызывает `_matherr` функция с именем функции, ее аргументы и тип ошибки. Можно переписать `_matherr` функции для обработки определенных ошибок во время выполнения вычисления с плавающей запятой.