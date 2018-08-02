---
title: Функция Abort | Документация Майкрософт
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
ms.openlocfilehash: 3e5679ce718c564ee40fb07b676756ef79344a99
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39403626"
---
# <a name="abort-function"></a>Функция abort

**Прервать** функция, также объявляется в стандартном включаемом файле \<stdlib.h >, завершает программу C++. Разница между `exit` и **прервать** является то, что `exit` позволяет обработка завершения среды выполнения C++ вступили в силу (глобальным объектом, будут вызваны деструкторы), тогда как **прервать** немедленно завершает программу. Дополнительные сведения см. в разделе [прервать](../c-runtime-library/reference/abort.md) в *Справочник по библиотеке времени выполнения*.

## <a name="see-also"></a>См. также
[Завершение программы](../cpp/program-termination.md)