---
title: "Функция Abort | Документы Microsoft"
ms.custom: 
ms.date: 12/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3fcd54b9aacf4eaba4bb5acfb115943225aa0efa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="abort-function"></a>Функция abort

**Прервать** функции, также объявляется в стандартном включаемом файле STDLIB. H, завершает программу C++. Разница между **выйти из** и **прервать** является то, что **выхода** происходит обработка завершения среды выполнения C++ (глобальных объектов, будут вызваны деструкторы), в то время как **прервать** программа завершается сразу. Дополнительные сведения см. в разделе [прервать](../c-runtime-library/reference/abort.md) в *Справочник по библиотеке времени выполнения*.

## <a name="see-also"></a>См. также

[Завершение программы](../cpp/program-termination.md)