---
title: Ошибка средств компоновщика LNK1164 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK1164
dev_langs:
- C++
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4b07dcf360a58b07b84abe655641b758d6137d0e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46087446"
---
# <a name="linker-tools-error-lnk1164"></a>Ошибка средств компоновщика LNK1164

раздел выравнивание разделов (number) больше, чем значение/ALIGN

Размер выравнивания для данного раздела в объектном файле превышает значение, указанное с помощью [/ALIGN](../../build/reference/align-section-alignment.md) параметр. **/ALIGN** значение должно быть степенью числа 2 и равняться или превышать выравнивание раздела, заданное в объектном файле.

Перекомпилируйте с меньшего размера выравнивание разделов или увеличение **/ALIGN** значение.