---
title: Ошибка средств компоновщика LNK1223 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1223
dev_langs:
- C++
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e50d29af6ac563fadd3a52e5b1d3d15201289083
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33298656"
---
# <a name="linker-tools-error-lnk1223"></a>Ошибка средств компоновщика LNK1223
недопустимый или поврежденный файл: файл содержит недопустимые фрагменты .pdata  
  
 Для RISC-платформ, использующих pdata, эта ошибка возникнет, если компилятор выдаст фрагмент .pdata с несортированными записями.  
  
 Чтобы устранить эту проблему, попробуйте компилировать без [/GL (оптимизация всей программы)](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) включена. Также в некоторых случаях эта ошибка может возникнуть из-за пустого текста функций.