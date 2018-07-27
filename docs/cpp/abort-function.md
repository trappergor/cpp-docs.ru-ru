---
title: Функция Abort | Документы Microsoft
ms.custom: ''
ms.date: 12/01/2017
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4acfbb5a0790dec6f7b5770832cc6b09f69a28d7
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408036"
---
# <a name="abort-function"></a>Функция abort

**Прервать** функции, также объявляется в стандартном включаемом файле \<stdlib.h >, завершает программу C++. Разница между **выйти из** и **прервать** является то, что **выхода** происходит обработка завершения среды выполнения C++ (глобальных объектов, будут вызваны деструкторы), в то время как **прервать** программа завершается сразу. Дополнительные сведения см. в разделе [прервать](../c-runtime-library/reference/abort.md) в *Справочник по библиотеке времени выполнения*.

## <a name="see-also"></a>См. также

[Завершение программы](../cpp/program-termination.md)