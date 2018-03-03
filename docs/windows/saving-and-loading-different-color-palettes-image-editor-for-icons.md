---
title: "Сохранение и загрузка различных цветовых палитр (редактор изображений для значков) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7ef7200300eb4809496bfa342e9bab645f4c40e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="saving-and-loading-different-color-palettes-image-editor-for-icons"></a>Сохранение и загрузка различных цветовых палитр (редактор изображений для значков)
Можно сохранить и загрузить палитру цветов, которая содержит [пользовательские цвета](../windows/customizing-or-changing-colors-image-editor-for-icons.md). (По умолчанию последняя использованная палитра цветов автоматически загружается при запуске Visual Studio.)  
  
> [!TIP]
>  Поскольку в редакторе изображений отсутствуют средства для восстановления палитры цветов по умолчанию, следует сохранять такую палитру цветов под специальным именем, например, standard.pal или default.pal, чтобы можно было легко восстановить параметры по умолчанию.  
  
### <a name="to-save-a-custom-colors-palette"></a>Сохранение пользовательской палитры цветов  
  
1.  Из **изображения** меню, выберите **сохранить палитру**.  
  
2.  Перейдите в каталог, в который требуется сохранить палитру, и введите имя палитры.  
  
3.  Нажмите кнопку **Сохранить**.  
  
### <a name="to-load-a-custom-colors-palette"></a>Загрузка пользовательской палитры цветов  
  
1.  Из **изображения** меню, выберите **Загрузить палитру**.  
  
2.  В [Загрузка цветов палитры-диалоговое окно](../windows/load-palette-colors-dialog-box-image-editor-for-icons.md), перейдите в нужный каталог и выберите палитру, которую требуется загрузить. Палитры цветов сохраняются в файлах с расширением PAL.  
  

  
 Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Работа с цветом](../windows/working-with-color-image-editor-for-icons.md)