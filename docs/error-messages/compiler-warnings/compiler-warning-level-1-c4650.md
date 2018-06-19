---
title: Предупреждение (уровень 1) C4650 компилятора | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4650
dev_langs:
- C++
helpviewer_keywords:
- C4650
ms.assetid: 3190b3e3-dcd6-4846-939b-f900ab652b2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6cb1c9979141e7958b6c2802aaf321efe41e9570
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33283089"
---
# <a name="compiler-warning-level-1-c4650"></a>Предупреждение компилятора (уровень 1) C4650
отладочная информация не включена в предкомпилированный заголовок; будут доступны только глобальные символы из заголовка  
  
 Файл предкомпилированного заголовка не была скомпилирована с символьной отладочной информации Майкрософт.  
  
 Когда он связан, полученный файл исполняемый или динамической библиотеки не войдут отладочную информацию для локальных символов, содержащихся в предкомпилированный заголовок.  
  
 Это предупреждение можно избежать путем повторной компиляции файла предкомпилированного заголовка с [/ZI](../../build/reference/z7-zi-zi-debug-information-format.md) параметр командной строки.