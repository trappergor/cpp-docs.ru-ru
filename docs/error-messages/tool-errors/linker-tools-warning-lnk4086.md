---
title: Предупреждение средств компоновщика LNK4086 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK4086
dev_langs:
- C++
helpviewer_keywords:
- LNK4086
ms.assetid: ea1eecbb-ba2c-41bb-9a4f-fa0808a4b92d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b7b3ad3a8ceebf97ccdcf7a1d8079886f54a3984
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="linker-tools-warning-lnk4086"></a>Предупреждение средств компоновщика LNK4086
точка входа «функция» не является __stdcall с 'number' байт аргументов; образ нельзя запустить  
  
 Точка входа для библиотеки DLL должна быть `__stdcall`. Либо повторите компиляцию функцию с [/Gz](../../build/reference/gd-gr-gv-gz-calling-convention.md) параметр или указать `__stdcall` или WINAPI при определении функции.