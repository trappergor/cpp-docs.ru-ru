---
title: /WINMDKEYFILE (укажите файл ключей winmd)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKeyFile
ms.assetid: 65d88fdc-fff9-49ea-8cfc-b2f408741734
ms.openlocfilehash: 4b0c847bc5be6c73b78af4aa15b0074c712cc840
ms.sourcegitcommit: faa42c8a051e746d99dcebe70fd4bbaf3b023ace
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/15/2019
ms.locfileid: "57820407"
---
# <a name="winmdkeyfile-specify-winmd-key-file"></a>/WINMDKEYFILE (укажите файл ключей winmd)

Указывает ключ или пару ключей для подписания файла метаданных среды выполнения Windows (.winmd).

```
/WINMDKEYFILE:filename
```

## <a name="remarks"></a>Примечания

Напоминает [/keyfile](keyfile-specify-key-or-key-pair-to-sign-an-assembly.md) параметра компоновщика, который применяется в winmd-файл.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **файл ключа метаданных Windows** введите нужный файл.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
