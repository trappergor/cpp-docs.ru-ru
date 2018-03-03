---
title: "Неустранимая ошибка компилятора ресурсов RC1052 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1052
dev_langs:
- C++
helpviewer_keywords:
- RC1052
ms.assetid: 59803673-492b-44fa-80fa-df93b8aaf9fb
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0546441022d8e2b487d83e291574020665cdaf4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1052"></a>Неустранимая ошибка компилятора ресурсов RC1052
предел компилятора : слишком глубокое вложение блоков #if или #ifdef  
  
 В программе превышен предельный уровень вложенности для директив `#if` и `#ifdef`.  
  
 Эта ошибка может быть вызвана включаемыми файлами, использующими директивы предварительной обработки.  
  
 Чтобы устранить эту проблему, нужно уменьшить количество вложенных директив `#if` и `#ifdef` в файле ресурсов. Если эта проблема вызвана файлами заголовков, включенных в файлах ресурсов, нужно  уменьшить количество вложенных директив `#if` и `#ifdef` в файлах заголовков. Если это невозможно, попробуйте создать и включить в файле ресурсов новый файл заголовка, выполнив предварительную обработку для существующих файлов заголовков. Дополнительные сведения см. в разделе [/P (Предварительная обработка в файл)](../../build/reference/p-preprocess-to-a-file.md) параметр компилятора.