---
title: "Ошибка средств компоновщика LNK1302 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK1302
dev_langs: C++
helpviewer_keywords: LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7154cc538e17050eafec251729cf26a3cd62e573
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="linker-tools-error-lnk1302"></a>Ошибка средств компоновщика LNK1302
поддерживается только компоновка безопасных .netmodule; не удалось связать файл NETMODULE-файл  
  
 .Netmodule (скомпилированный с **/LN**) был передан компоновщику пользователя при попытке вызвать компоновку MSIL.  Модуль C++ является допустимым компоновка MSIL, если она скомпилирована с **/CLR: safe**.  
  
 Чтобы исправить эту ошибку, компиляция с **/CLR: safe** Чтобы включить компоновку MSIL, либо передайте **/CLR** или **/CLR: pure** вместо модуле компоновщик OBJ-файл.  
  
 Дополнительные сведения см. в разделе .  
  
-   [/LN (Создание модуля MSIL)](../../build/reference/ln-create-msil-module.md)  
  
-   [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md)