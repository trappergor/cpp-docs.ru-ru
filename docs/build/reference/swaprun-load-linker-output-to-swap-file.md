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
ms.openlocfilehash: bd0b3a46f52ec9b5a292e2f45671523d8c5cdf5e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62317553"
---
# <a name="swaprun-load-linker-output-to-swap-file"></a>/SWAPRUN (загрузка выходных данных компоновщика в файл подкачки)

```
/SWAPRUN:{NET|CD}
```

## <a name="remarks"></a>Примечания

Параметр/SWAPRUN предписывает операционной системе сначала Копировать компоновщика выходные данные в файл подкачки, а затем запускать образ оттуда. Эта функция Windows NT 4.0 (и более поздние версии).

Если задан параметр NET, операционная система сначала копирует двоичный образ из сети в файл подкачки и загрузить его оттуда. Этот параметр полезен для запуска приложений по сети. Когда задан компакт-ДИСК, операционная система будет скопировать образ на съемном диске файл подкачки и последующей ее загрузки.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Задание данного параметра компоновщика в среде разработки Visual Studio

1. Откройте диалоговое окно **Страницы свойств** проекта. Дополнительные сведения см. в разделе [свойств компилятора и собранной задать C++ в Visual Studio](../working-with-project-properties.md).

1. Нажмите кнопку **компоновщика** папки.

1. Нажмите кнопку **системы** страницу свойств.

1. Измените одно из следующих свойств:

   - **Запускать файла подкачки с компакт-диска**

   - **Запускать файла подкачки из сети**

### <a name="to-set-this-linker-option-programmatically"></a>Задание данного параметра компоновщика программным способом

1. См. описание свойств <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromCD%2A> и <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.SwapRunFromNet%2A>.

## <a name="see-also"></a>См. также

[Справочник по компоновщику MSVC](linking.md)<br/>
[Параметры компоновщика MSVC](linker-options.md)
