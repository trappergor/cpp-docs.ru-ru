---
title: "Ошибка компилятора ресурсов RC2101 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC2101
dev_langs:
- C++
helpviewer_keywords:
- RC2101
ms.assetid: 580f9d74-162f-41e9-9438-ddbe3457c359
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 686c0b218ac4260fb796f60c1484c576a0c805b9
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="resource-compiler-error-rc2101"></a>Ошибка компилятора ресурсов RC2101
Недопустимая директива в предварительно обработанном RC-файле  
  
 Файл компилятора ресурсов содержит **#pragma** директивы.  
  
 Используйте **#ifndef** директива препроцессора с константой RC_INVOKED, которую компилятор ресурсов задает при обработке включаемого файла. Место **#pragma** директив в блок кода, который не обрабатывается при заданной константе RC_INVOKED. Код в блоке, обрабатываются только компилятором C или C++ и не компилятором ресурсов. В следующем примере кода показана эта технология:  
  
```  
#ifndef RC_INVOKED  
#pragma pack(2)  // C/C++ only, ignored by Resource Compiler  
#endif  
```  
  
 **#Pragma** директивы препроцессора не имеет смысла в. RC-файле. **#Include** в часто используется директива препроцессора. RC-файле для включения файла заголовка (на основе проекта пользовательского заголовка файла или стандартный заголовок файла, предоставленного корпорацией Майкрософт с одним из продуктов). Некоторые из этих включаемых файлов содержат **#pragma** директивы. Поскольку файл заголовка может включать один или несколько других файлов заголовков, файл, содержащий функция **#pragma** директива может оказаться неочевидным.  
  
 **#Ifndef** RC_INVOKED может управлять включением файлов заголовков в файлы заголовков проекта.
