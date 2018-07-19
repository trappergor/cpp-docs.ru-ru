---
title: Ввод и вывод | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- c.io
dev_langs:
- C++
helpviewer_keywords:
- input routines
- I/O [CRT]
- I/O routines
- I/O [CRT], routines
- output routines
ms.assetid: 1c177301-e341-4ca0-aedc-0a87fe1c75ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e62319d040275d96314ee824f9fea020a4004974
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32389395"
---
# <a name="input-and-output"></a>Ввод и вывод

Функции ввода-вывода производят чтение из файлов и устройств и запись в них. Операции файлового ввода-вывода выполняются в текстовом или двоичном режиме. Библиотека времени выполнения Microsoft содержит три типа функций ввода-вывода:

- Функции [потокового ввода-вывода](../c-runtime-library/stream-i-o.md) обрабатывают данные как поток отдельных символов.

- Функции [низкоуровневого ввода-вывода](../c-runtime-library/low-level-i-o.md) напрямую вызывают операционную систему для выполнения операций более низкого уровня, чем поддерживаемые при потоковом вводе-выводе.

- Функции [ввода-вывода на консоль и в порты](../c-runtime-library/console-and-port-i-o.md) производят чтение или запись непосредственно на консоль (клавиатуру и экран) или в порт ввода-вывода (например, порт принтера).

   > [!NOTE]
   > Поскольку потоковые функции используют буфер, а низкоуровневые функции буфер не используют, эти два типа функций обычно несовместимы. Для обработки конкретного файла используйте либо только потоковые, либо только низкоуровневые функции.

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
