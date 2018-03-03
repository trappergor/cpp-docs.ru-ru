---
title: "Предупреждение (уровень 1) C4650 компилятора | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: af10d05562c0c60c6a010e105441533362d058df
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4650"></a>Предупреждение компилятора (уровень 1) C4650
отладочная информация не включена в предкомпилированный заголовок; будут доступны только глобальные символы из заголовка  
  
 Файл предкомпилированного заголовка не была скомпилирована с символьной отладочной информации Майкрософт.  
  
 Когда он связан, полученный файл исполняемый или динамической библиотеки не войдут отладочную информацию для локальных символов, содержащихся в предкомпилированный заголовок.  
  
 Это предупреждение можно избежать путем повторной компиляции файла предкомпилированного заголовка с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр командной строки.