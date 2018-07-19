---
title: / INTEGRITYCHECK | Документы Microsoft
ms.custom: ''
ms.date: 12/28/2017
ms.technology:
- cpp-tools
ms.topic: reference
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
ms.workload:
- cplusplus
ms.openlocfilehash: 4b0adf9add2d191ae89aec0a5d756ade8e9f7725
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32370252"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Указывает, что цифровая подпись двоичный образ будет выполняться проверка во время загрузки.

> **/ INTEGRITYCHECK-**[**: НЕТ**]

## <a name="remarks"></a>Примечания

В заголовке файла DLL или исполняемого файла этот параметр устанавливает флаг, который требует проверки цифровой подписи диспетчером памяти для загрузки изображения в Windows. Версии Windows, предшествующей Windows Vista игнорировать этот флаг. Этот параметр необходимо задать для 64-разрядных библиотек DLL, реализующие кода в режиме ядра и рекомендуется для всех драйверов устройств. Дополнительные сведения см. в разделе [требования к подписи кода в режиме ядра](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)  
