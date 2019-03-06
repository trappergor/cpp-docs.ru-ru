---
title: /SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.SwapRunFromNet
- /swaprun
- VC.Project.VCLinkerTool.SwapRunFromCD
helpviewer_keywords:
- -SWAPRUN linker option
- files [C++], LINK
- LINK tool [C++], output
- linker [C++], copying output to swap file
- swap file for linker output
- output files, linker
- /SWAPRUN linker option
- SWAPRUN linker option
ms.assetid: 4a1e7f46-4399-4161-8dfc-d6a71beaf683
ms.openlocfilehash: 085be83bf73288871c71bef00378ddd494cd6f8d
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57424877"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Примечания

Параметр/SWAPRUN предписывает операционной системе сначала Копировать компоновщика выходные данные в файл подкачки, а затем запускать образ оттуда. Эта функция Windows NT 4.0 (и более поздние версии).

Если задан параметр NET, операционная система сначала копирует двоичный образ из сети в файл подкачки и загрузить его оттуда. Этот параметр полезен для запуска приложений по сети. Когда задан компакт-ДИСК, операционная система будет скопировать образ на съемном диске файл подкачки и последующей ее загрузки.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств проекта Visual C++ параметр](../../ide/working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Измените одно из следующих свойств:

   - **Запускать файла подкачки с компакт-диска**

   - **Запускать файла подкачки из сети**

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.

## <a name="see-also"></a>См. также

[Настройка параметров компоновщика](../../build/reference/setting-linker-options.md)<br/>
[Параметры компоновщика](../../build/reference/linker-options.md)
