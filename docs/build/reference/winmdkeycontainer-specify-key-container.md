---
title: /WINMDKEYCONTAINER (указать контейнер ключей)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.WINMDKEYCONTAINER
ms.assetid: c2fc44dc-7cb5-42b9-897f-1b124928f2f7
ms.openlocfilehash: 0b6cb42fc391d94634ae90e5a4cc17e69a14ff09
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57813075"
---
# <a name="winmdkeycontainer-specify-key-container"></a>/WINMDKEYCONTAINER (указать контейнер ключей)

Задает контейнер ключа для подписывания файла метаданных Windows (.winmd).

```
/WINMDKEYCONTAINER:name
```

## <a name="remarks"></a>Примечания

Напоминает [/keycontainer](keycontainer-specify-a-key-container-to-sign-an-assembly.md) параметра компоновщика, который применяется в файл (с расширением winmd).

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Выберите **компоновщика** папки.

1. Выберите **метаданных Windows** страницу свойств.

1. В **контейнер ключа метаданных Windows** введите расположение.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
