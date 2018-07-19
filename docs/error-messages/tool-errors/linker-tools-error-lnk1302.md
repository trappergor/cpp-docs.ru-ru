---
title: Ошибка средств компоновщика LNK1302 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1302
dev_langs:
- C++
helpviewer_keywords:
- LNK1302
ms.assetid: aea3c753-c2c4-4249-bbc3-f2d4f0164b5e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6aa84a411f91303c84acb44e2e6c0ab3d975e19f
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33299423"
---
# <a name="linker-tools-error-lnk1302"></a>Ошибка средств компоновщика LNK1302
поддерживается только компоновка безопасных .netmodule; не удалось связать файл NETMODULE-файл  
  
 .Netmodule (скомпилированный с **/LN**) был передан компоновщику пользователя при попытке вызвать компоновку MSIL.  Модуль C++ является допустимым компоновка MSIL, если она скомпилирована с **/CLR: safe**.  
  
 Чтобы исправить эту ошибку, компиляция с **/CLR: safe** Чтобы включить компоновку MSIL, либо передайте **/CLR** или **/CLR: pure** вместо модуле компоновщик OBJ-файл.  
  
 Дополнительные сведения см. в разделе .  
  
-   [/LN (создание модуля MSIL)](../../build/reference/ln-create-msil-module.md)  
  
-   [NETMODULE-файлы в качестве входных файлов компоновщика](../../build/reference/netmodule-files-as-linker-input.md)