---
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: 4174e22dcdadb3b3319998614285c13741fe3a88
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814253"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Указывает, что цифровая подпись бинарного образа должна быть проверена во время загрузки.

> **/ INTEGRITYCHECK**[**: НЕТ**]

## <a name="remarks"></a>Примечания

В заголовке исполняемого файла или файла DLL этот параметр устанавливает флаг, требующий проверки цифровой подписи диспетчером памяти для загрузки образа в Windows. Версии Windows до Windows Vista игнорируют этот флажок. Этот параметр необходимо задать для 64-разрядных библиотек DLL, которые реализуют кода режима ядра и рекомендуется для всех драйверов устройств. Дополнительные сведения см. в разделе [требования подписывания кода режима ядра](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>См. также

[Параметры EDITBIN](editbin-options.md)
