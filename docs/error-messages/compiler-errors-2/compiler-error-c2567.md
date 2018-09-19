---
title: Ошибка компилятора C2567 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2567
dev_langs:
- C++
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cb09aacc1b81e9f0e0c9c96a496eccc89a061f37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46104249"
---
# <a name="compiler-error-c2567"></a>Ошибка компилятора C2567

не удается открыть метаданные в «файл», файл может перемещены или удалены

Файл метаданных, на который была ссылка в источнике (с `#using`) не найден в том же каталоге процессом серверной части компилятора, которая была процессом компилятора внешнего интерфейса. См. в разделе [# директива using](../../preprocessor/hash-using-directive-cpp.md) Дополнительные сведения.

C2567 может возникать, если компиляция выполняется с **/c** на одном компьютере и затем попытка создания кода времени компоновки на другом компьютере. Дополнительные сведения см. в разделе [/LTCG (Создание кода во время компоновки)](../../build/reference/ltcg-link-time-code-generation.md)).

Кроме того, это может указывать на нехватку памяти.

Чтобы исправить эту ошибку, убедитесь, что файл метаданных находится в той же папке каталогов для всех этапов процесса сборки.