---
title: "/ INTEGRITYCHECK | Документы Microsoft"
ms.custom: 
ms.date: 12/28/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- /INTEGRITYCHECK
dev_langs:
- C++
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 99caec18162a7506b8b7a467eb7374b6fe4a38d9
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/03/2018
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Указывает, что цифровая подпись двоичный образ будет выполняться проверка во время загрузки.

> **/ INTEGRITYCHECK-**[**: НЕТ**]

## <a name="remarks"></a>Примечания

В заголовке файла DLL или исполняемого файла этот параметр устанавливает флаг, который требует проверки цифровой подписи диспетчером памяти для загрузки изображения в Windows. Версии Windows, предшествующей Windows Vista игнорировать этот флаг. Этот параметр необходимо задать для 64-разрядных библиотек DLL, реализующие кода в режиме ядра и рекомендуется для всех драйверов устройств. Дополнительные сведения см. в разделе [требования к подписи кода в режиме ядра](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)  
