---
title: Неустранимая ошибка C1099 | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C1099
dev_langs:
- C++
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d97bed1bdc81c738ff20bb85038153181ddb06ee
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="fatal-error-c1099"></a>Неустранимая ошибка C1099
Механизм "Изменить и продолжить" прервал компиляцию  
  
 Компонент "Изменить и продолжить" загрузил предварительно скомпилированный файл заголовка при подготовке к компиляции изменений кода, но последующие действия (например, изменения кода до оператора предварительно скомпилированного заголовка `#include` или остановка отладчика) помешали компоненту "Изменить и продолжить" завершить компиляцию в этом процессе. Не нужно предпринимать никаких действий, чтобы устранить эту ошибку.