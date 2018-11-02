---
title: /WINMDKEYFILE (укажите файл ключей winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 076533278bb9b8ec2838cfb719bcb4df1784b258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436795"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (укажите файл ключей winmd)

Указывает ключ или пару ключей для подписания файла метаданных среды выполнения Windows (.winmd).

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Примечания

Напоминает [/keyfile](../../build/reference/keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) параметра компоновщика, который применяется в winmd-файл.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [Работа со свойствами проекта](../../ide/working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **файл ключа метаданных Windows** введите нужный файл.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)