---
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b3f6622e3628db53c363b239c59accd94f708ab0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617279"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Указывает, что цифровая подпись бинарного образа должна быть проверена во время загрузки.

> **/ INTEGRITYCHECK**[**: НЕТ**]

## <a name="remarks"></a>Примечания

В заголовке исполняемого файла или файла DLL этот параметр устанавливает флаг, требующий проверки цифровой подписи диспетчером памяти для загрузки образа в Windows. Версии Windows до Windows Vista игнорируют этот флажок. Этот параметр необходимо задать для 64-разрядных библиотек DLL, которые реализуют кода режима ядра и рекомендуется для всех драйверов устройств. Дополнительные сведения см. в разделе [требования подписывания кода режима ядра](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)
