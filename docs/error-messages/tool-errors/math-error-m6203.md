---
title: "Математическая ошибка M6203 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- M6203
dev_langs:
- C++
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f65e016a736113ea4bcb9e488e792daa673d00d7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="math-error-m6203"></a>Математическая ошибка M6203
«функция»: ошибка _OVERFLOW  
  
 Результат заданной функции слишком велико для представления.  
  
 Эта ошибка вызывает `_matherr` функция с именем функции, ее аргументы и тип ошибки. Можно переписать `_matherr` функции для обработки определенных ошибок во время выполнения вычисления с плавающей запятой.