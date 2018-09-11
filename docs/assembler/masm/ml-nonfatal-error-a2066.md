---
title: Некритичная ошибка ML A2066 | Документация Майкрософт
ms.custom: ''
ms.date: 08/30/2018
ms.technology:
- cpp-masm
ms.topic: error-reference
f1_keywords:
- A2066
dev_langs:
- C++
helpviewer_keywords:
- A2066
ms.assetid: 58220fdf-fb8f-47fc-a36d-737867361185
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8cf5cbe7d5c77da7f129cbc40ffa97f4051afca6
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/04/2018
ms.locfileid: "43690256"
---
# <a name="ml-nonfatal-error-a2066"></a>Некритичная ошибка ML A2066

**несовместимые размер режим и сегмент ЦП**

Была предпринята попытка открыть сегмент с **USE16**, **USE32**, или **НЕСТРУКТУРИРОВАННЫЙ** атрибут, который несовместим с указанным ЦП или изменить ЦП 16-разрядное в 32-разрядное Сегмент.

**USE32** и **НЕСТРУКТУРИРОВАННЫЙ** атрибуты должен предшествовать.386 или больше директивы процессора.

## <a name="see-also"></a>См. также

[Сообщения об ошибках ML](../../assembler/masm/ml-error-messages.md)<br/>