---
title: "Неустранимая ошибка C1099 | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C1099
dev_langs:
- C++
helpviewer_keywords:
- C1099
ms.assetid: c050b074-a06a-4026-9e10-569029cc0739
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 928ced6fe9e283cf16db651ecbf6164164e3174e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1099"></a>Неустранимая ошибка C1099
Механизм "Изменить и продолжить" прервал компиляцию  
  
 Компонент "Изменить и продолжить" загрузил предварительно скомпилированный файл заголовка при подготовке к компиляции изменений кода, но последующие действия (например, изменения кода до оператора предварительно скомпилированного заголовка `#include` или остановка отладчика) помешали компоненту "Изменить и продолжить" завершить компиляцию в этом процессе. Не нужно предпринимать никаких действий, чтобы устранить эту ошибку.