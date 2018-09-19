---
title: Ошибка компилятора C3859 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3859
dev_langs:
- C++
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1ac06a09a6ad66384fd2b5423e3df046771f7653
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053393"
---
# <a name="compiler-error-c3859"></a>Ошибка компилятора C3859

превышен диапазон адресов виртуальной памяти для PCH; повторите компиляцию с параметром командной строки "-Zmvalue" или большим

Предкомпилированный заголовок слишком мал для объема данных, который компилятор пытается в него поместить. Используйте **/Zm** флаг компилятора, чтобы указать большее значение для предкомпилированного файла заголовка. Дополнительные сведения см. в разделе [/Zm (укажите предкомпилированный заголовок предел выделения памяти)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).