---
title: Функция abort
ms.date: 12/01/2017
helpviewer_keywords:
- abort function
ms.assetid: 3352bcc4-1a8a-4e1f-8dcc-fe30f6b50f2d
ms.openlocfilehash: 7c87cb4fe7349a0d623c765c20e7e213a8454571
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50451237"
---
# <a name="abort-function"></a>Функция abort

**Прервать** функция, также объявляется в стандартном включаемом файле \<stdlib.h >, завершает программу C++. Разница между `exit` и **прервать** является то, что `exit` позволяет обработка завершения среды выполнения C++ вступили в силу (глобальным объектом, будут вызваны деструкторы), тогда как **прервать** немедленно завершает программу. Дополнительные сведения см. в разделе [прервать](../c-runtime-library/reference/abort.md) в *Справочник по библиотеке времени выполнения*.

## <a name="see-also"></a>См. также

[Завершение программы](../cpp/program-termination.md)