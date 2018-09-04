---
title: Надежность | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.runtime
dev_langs:
- C++
helpviewer_keywords:
- robustness [CRT]
ms.assetid: 7f1a87f8-eff9-4b76-ae9b-d133d3de6adf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4bc7ac76377ef59c9b1f5535f356b35d88a5e4e
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43220963"
---
# <a name="robustness"></a>Устойчивость

Используйте следующие функции библиотеки времени выполнения языка C, чтобы повысить надежность своей программы.

## <a name="run-time-robustness-functions"></a>Функции повышения надежности во время выполнения

|Функция|Использовать|
|--------------|---------|
|[_set_new_handler](../c-runtime-library/reference/set-new-handler.md)|Передает управление механизму обработки ошибок, если оператору **new** не удается выделить память.|
|[_set_se_translator](../c-runtime-library/reference/set-se-translator.md)|Обрабатывает исключения Win32 (структурированные исключения C) как типизированные исключения C++.|
|[set_terminate](../c-runtime-library/reference/set-terminate-crt.md)|Устанавливает собственную функцию завершения, которая будет вызываться [terminate](../c-runtime-library/reference/terminate-crt.md).|
|[set_unexpected](../c-runtime-library/reference/set-unexpected-crt.md)|Устанавливает собственную функцию завершения, которая будет вызываться [unexpected](../c-runtime-library/reference/unexpected-crt.md).|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
 [SetUnhandledExceptionFilter](https://msdn.microsoft.com/library/windows/desktop/ms680634.aspx)<br/>
