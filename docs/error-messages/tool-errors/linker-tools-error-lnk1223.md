---
title: "Ошибка средств компоновщика LNK1223 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK1223
dev_langs:
- C++
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c330077e8de73b8eeb71b0a418eb89d2ec0ebfdc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk1223"></a>Ошибка средств компоновщика LNK1223
недопустимый или поврежденный файл: файл содержит недопустимые фрагменты .pdata  
  
 Для RISC-платформ, использующих pdata, эта ошибка возникнет, если компилятор выдаст фрагмент .pdata с несортированными записями.  
  
 Чтобы устранить эту проблему, попробуйте компилировать без [/GL (оптимизация всей программы)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) включена. Также в некоторых случаях эта ошибка может возникнуть из-за пустого текста функций.