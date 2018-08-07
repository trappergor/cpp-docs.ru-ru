---
title: Сохранение и загрузка различных цветовых палитр (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.image.color
dev_langs:
- C++
helpviewer_keywords:
- color palettes [C++]
- palettes
- palettes, Image editor
- colors [C++], Image editor
- Image editor [C++], palettes
ms.assetid: 694b6346-e606-4f19-aa01-9b4ceb47f423
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 14cad19c53e8cd741bf16bab49420169e93f6af6
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606976"
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Сохранение и загрузка различных цветовых палитр (редактор изображений для значков)
Можно сохранить и загрузить палитру цветов, которая содержит [настраивать цвета](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (По умолчанию последняя использованная палитра цветов автоматически загружается при запуске Visual Studio.)  
  
> [!TIP]
>  Поскольку в редакторе изображений отсутствуют средства для восстановления палитры цветов по умолчанию, следует сохранять такую палитру цветов под специальным именем, например, standard.pal или default.pal, чтобы можно было легко восстановить параметры по умолчанию.  
  
### <a name="to-save-a-custom-colors-palette"></a>Сохранение пользовательской палитры цветов  
  
1.  Из **изображение** меню, выберите **сохранить палитру**.  
  
2.  Перейдите в каталог, в который требуется сохранить палитру, и введите имя палитры.  
  
3.  Нажмите кнопку **Сохранить**.  
  
### <a name="to-load-a-custom-colors-palette"></a>Загрузка пользовательской палитры цветов  
  
1.  Из **изображение** меню, выберите **Загрузка палитры**.  
  
2.  В [Загрузка палитры цветов-диалоговое окно](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), перейдите в нужный каталог и выберите палитру, которую нужно загрузить. Палитры цветов сохраняются в файлах с расширением PAL.  
  
## <a name="requirements"></a>Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Работа с цветом](../windows/working-with-color-image-editor-for-icons.md)