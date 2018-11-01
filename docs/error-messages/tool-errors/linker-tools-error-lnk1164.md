---
title: Ошибка средств компоновщика LNK1164
ms.date: 11/04/2016
f1_keywords:
- LNK1164
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
ms.openlocfilehash: 8685a9e0eb356719eaab129af9df9a1cc0ebb085
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585501"
---
# <a name="linker-tools-error-lnk1164"></a>Ошибка средств компоновщика LNK1164

раздел выравнивание разделов (number) больше, чем значение/ALIGN

Размер выравнивания для данного раздела в объектном файле превышает значение, указанное с помощью [/ALIGN](../../build/reference/align-section-alignment.md) параметр. **/ALIGN** значение должно быть степенью числа 2 и равняться или превышать выравнивание раздела, заданное в объектном файле.

Перекомпилируйте с меньшего размера выравнивание разделов или увеличение **/ALIGN** значение.