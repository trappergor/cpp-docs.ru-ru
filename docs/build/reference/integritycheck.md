---
title: / INTEGRITYCHECK | Документация Майкрософт
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
ms.openlocfilehash: 062ce019fe1b622661be880d8a06eac9c5971103
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45709207"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

Указывает, что цифровая подпись бинарного образа должна быть проверена во время загрузки.

> **/ INTEGRITYCHECK**[**: НЕТ**]

## <a name="remarks"></a>Примечания

В заголовке исполняемого файла или файла DLL этот параметр устанавливает флаг, требующий проверки цифровой подписи диспетчером памяти для загрузки образа в Windows. Версии Windows до Windows Vista игнорируют этот флажок. Этот параметр необходимо задать для 64-разрядных библиотек DLL, которые реализуют кода режима ядра и рекомендуется для всех драйверов устройств. Дополнительные сведения см. в разделе [требования подписывания кода режима ядра](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-).

## <a name="see-also"></a>См. также

[Параметры EDITBIN](../../build/reference/editbin-options.md)
