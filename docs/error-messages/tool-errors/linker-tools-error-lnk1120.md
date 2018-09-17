---
title: Ошибка средств компоновщика LNK1120 | Документация Майкрософт
ms.custom: ''
ms.date: 05/17/2017
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1120
dev_langs:
- C++
helpviewer_keywords:
- LNK1120
ms.assetid: 56aa7d36-921f-4daf-b44d-cca0d4fb1b51
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f1d2a55d683e9c8b9d6a0da2b3e5fa78d5a39933
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45725573"
---
# <a name="linker-tools-error-lnk1120"></a>Ошибка средств компоновщика LNK1120

> *номер* неразрешенные внешние элементы  
  
Ошибка LNK1120 сообщает число (*номер*) ошибок неразрешенный внешний символ для этой операции связывания. Большинство неразрешенного внешнего символа ошибки выводятся отдельно пользователем [Ошибка средств компоновщика LNK2001](../../error-messages/tool-errors/linker-tools-error-lnk2001.md) и [Ошибка средств компоновщика LNK2019](../../error-messages/tool-errors/linker-tools-error-lnk2019.md), который предшествовать это сообщение об ошибке, один раз для каждого неразрешенные внешние элементы Ошибка символов.  
  
Чтобы устранить эту ошибку, исправьте все остальные неразрешенных внешних ошибки или другие ошибки компоновщика, расположенные перед ним в выходные данные сборки. Эта ошибка не выводится, когда остаются ошибки неразрешенных внешних.  
