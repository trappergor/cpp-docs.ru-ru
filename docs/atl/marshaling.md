---
title: Маршалинг | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- marshaling, COM interop
- marshaling
- COM interfaces, marshaling
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 69f1b7e131b614aa4714f0c2be19fab79982031c
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46108629"
---
# <a name="marshaling"></a>Маршалинг

Метод COM маршалинга можно использовать интерфейсы, предоставляемые объектом в рамках одного процесса для использования в другом процессе. При маршалинге, предоставляет код COM (или использует код, предоставленный средством реализации интерфейса) для упаковки параметров метода в формат, который можно перемещать между процессами (а также, по каналу связи процессов, выполняющихся на других компьютерах) и Распаковка этих параметров на другом конце. Аналогичным образом эти же действия необходимо выполнить COM, при возврате из вызова.

> [!NOTE]
>  Маршалинг обычно не является обязательным при интерфейс, предоставляемый объект используется в том же процессе, что и объект. Тем не менее маршалинг будет требоваться между потоками.

## <a name="see-also"></a>См. также

[Введение в модель COM](../atl/introduction-to-com.md)<br/>
[Сведения о маршалинге](/windows/desktop/com/marshaling-details)

