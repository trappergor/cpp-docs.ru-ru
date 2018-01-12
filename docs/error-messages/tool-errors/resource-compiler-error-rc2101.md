---
title: "Ошибка компилятора ресурсов RC2101 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC2101
dev_langs: C++
helpviewer_keywords: RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d08e9ddb7b8cda127b1d05bfef52b52833534cb2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-error-rc2101"></a>Ошибка компилятора ресурсов RC2101
Недопустимая директива в предварительно обработанный RC-файле  
  
 Файл компилятора ресурсов содержит **#pragma** директивы.  
  
 Используйте **#ifndef** директива препроцессора с константой RC_INVOKED, которую задает компилятор ресурсов при обработке файла включения. Место **#pragma** директив в блок кода, которые не обрабатываются, когда константе RC_INVOKED. Код в блоке, обрабатываются только компилятором C или C++ и не компилятором ресурсов. Этот метод продемонстрирован в следующем примере кода:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma** директиве препроцессора не имеет смысла в. RC-файле. **#Include** директива препроцессора часто используется в. RC-файле для включения файла заголовка (файл пользовательского заголовка на основе проекта или файла стандартный заголовок, предоставленного корпорацией Майкрософт с одним из продуктов). Некоторые из этих включаемых файлов содержат **#pragma** директивы. Поскольку файл заголовка может включать один или несколько других файлов заголовков, файл, содержащий функция **#pragma** директива может оказаться неочевидным.  
  
 **#Ifndef** RC_INVOKED может управлять включением файлов заголовков в файлы заголовков проекта.