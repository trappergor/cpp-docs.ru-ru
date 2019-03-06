---
title: /LARGEADDRESSAWARE (Обрабатывать большие адреса)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.LargeAddressAware
- /largeaddressaware
helpviewer_keywords:
- LARGEADDRESSAWARE linker option
- -LARGEADDRESSAWARE linker option
- /LARGEADDRESSAWARE linker option
ms.assetid: a29756c8-e893-47a9-9750-1f0d25359385
ms.openlocfilehash: 9ea26a87ce85f71188ca77345e4af055d3ffbf0e
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57413749"
---
# <a name="largeaddressaware-handle-large-addresses"></a>/LARGEADDRESSAWARE (Обрабатывать большие адреса)

```
/LARGEADDRESSAWARE[:NO]
```

## <a name="remarks"></a>Примечания

Параметр/LARGEADDRESSAWARE сообщает компоновщику о том, что приложение может обрабатывать адреса размером более 2 ГБ. В 64-разрядные компиляторы этот параметр включен по умолчанию. В 32-разрядные компиляторы: No включен, если/LARGEADDRESSAWARE не задан в строке компоновщика.

Если приложение было скомпоновано с/LARGEADDRESSAWARE, DUMPBIN [/Headers](../../build/reference/headers.md) будут отображаться сведения об этом.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Изменить **включить большие адреса** свойство.

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

- См. раздел <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LargeAddressAware%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
