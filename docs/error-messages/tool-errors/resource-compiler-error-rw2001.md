---
title: "Ошибка компилятора ресурсов RW2001 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RW2001
dev_langs: C++
helpviewer_keywords: RW2001
ms.assetid: 963bdc7d-6ebe-4378-8bbc-47dfcf5d330c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1a14cd36ab87297cf5bc0aa547bdea5ef23260e8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rw2001"></a>Ошибка компилятора ресурсов RW2001
Недопустимая директива в предварительно обработанный RC-файле  
  
 RC-файле содержится **#pragma** директивы.  
  
 Используйте **#ifndef** директива препроцессора с **RC_INVOKED** констант, компилятор ресурсов задает при обработке включаемого файла. Место **#pragma** директив в блок кода, не обрабатываются, если **RC_INVOKED** определена константа. Код в блоке, обрабатываются только компилятором C или C++ и не компилятором ресурсов. Этот метод продемонстрирован в следующем примере кода:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma** директиве препроцессора не имеет смысла в. RC-файле. **#Include** директива препроцессора часто используется в. RC-файле для включения файла заголовка (файл пользовательского заголовка на основе проекта или файла стандартный заголовок, предоставленного корпорацией Майкрософт с одним из продуктов). Некоторые из этих включаемых файлов содержат **#pragma** директивы. Поскольку файл заголовка может включать один или несколько других файлов заголовков, файл, содержащий функция **#pragma** директива может оказаться неочевидным.  
  
 **#Ifndef RC_INVOKED** методика помогает управлять включением файлов заголовков в файлы заголовков проекта.