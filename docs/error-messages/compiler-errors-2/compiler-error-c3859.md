---
title: Ошибка компилятора C3859
ms.date: 11/04/2016
f1_keywords:
- C3859
helpviewer_keywords:
- C3859
ms.assetid: 40e93b25-4393-4467-90de-035434a665c7
ms.openlocfilehash: be6ccaab49cb329e862fb6068af1337eddbaac8f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50490286"
---
# <a name="compiler-error-c3859"></a>Ошибка компилятора C3859

превышен диапазон адресов виртуальной памяти для PCH; повторите компиляцию с параметром командной строки "-Zmvalue" или большим

Предкомпилированный заголовок слишком мал для объема данных, который компилятор пытается в него поместить. Используйте **/Zm** флаг компилятора, чтобы указать большее значение для предкомпилированного файла заголовка. Дополнительные сведения см. в разделе [/Zm (укажите предкомпилированный заголовок предел выделения памяти)](../../build/reference/zm-specify-precompiled-header-memory-allocation-limit.md).