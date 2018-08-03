---
title: Создание прозрачных областей или обратный областей на изображениях устройств (редактор изображений для значков) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- cursors [C++], screen regions
- inverse colors, device images
- transparent regions, device images
- transparency, device images
- Image editor [C++], device images
- inverse regions, device images
- cursors [C++], transparent regions
- screen colors
- regions, transparent
- icons [C++], transparent regions
- display devices, transparent and screen regions
- transparent regions in devices
- regions, inverse
- colors [C++], Image editor
- device projects, transparent images
- icons [C++], screen regions
ms.assetid: a994954b-b039-4391-a535-58d1fa10fc3b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c8ebecf984254175a15075e8d8a4125f9fc5ec17
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462538"
---
# <a name="creating-transparent-or-inverse-regions-in-device-images-image-editor-for-icons"></a>Создание прозрачных областей или областей с обращенными цветами на изображениях устройств (редактор изображений для значков)
В [редактор изображений](../windows/image-editor-for-icons.md), начальной изображение значка или курсора имеют атрибут прозрачности. Несмотря на то, что изображения имеют прямоугольную форму, многие не отображаются, так как части изображения прозрачны. основное изображение на экране показаны через значка или курсора. При перетаскивании значка части изображения могут появиться в Инвертированный цвет. Создайте этот эффект, задавая цвет экрана и инвертированный цвет в [окно "цвета"](../windows/colors-window-image-editor-for-icons.md).  
  
 Цвета экрана и инвертированный применяется значки и курсоры либо фигуры и цвет производных изображений или назначить инвертирование областей. Цвета обозначают части изображения, исходя из этих атрибутов. Можно изменить цвета, которые представляют атрибуты цвет экрана и инвертированный цвет в редактирования. Эти изменения не влияют на внешний вид значка или курсора в приложении.  
  
> [!NOTE]
>  Отображаемые диалоговые окна и команды меню могут отличаться от описанных в справке в зависимости от текущих параметров или выпуска. Чтобы изменить параметры, выберите в меню **Сервис** пункт **Импорт и экспорт параметров** . Дополнительные сведения см. в статье [Настройка параметров разработки в Visual Studio](http://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
### <a name="to-create-transparent-or-inverse-regions"></a>Создание прозрачных областей или обратный областей  
  
1.  В **цвета** окно, нажмите кнопку **цвет экрана** селектор или **Инвертированный цвет** селектор.  
  
2.  Примените экрана или инвертированный цвет с помощью инструмента рисования. Дополнительные сведения об инструментах рисования см. в разделе [с помощью инструмента рисования](using-a-drawing-tool-image-editor-for-icons.md).  
  
### <a name="to-change-the-screen-or-inverse-color"></a>Чтобы изменить цвет экрана или обратное  
  
1.  Выберите либо **цвет экрана** селектор или **Инвертированный цвет** селектор.  
  
2.  Выберите цвет из **цвета** палитру в **цвета** окна.  
  
     Дополнительный цвет автоматически назначается для других селектора.  
  
    > [!TIP]
    >  Если дважды щелкнуть селектор цвета экрана и инвертированный цвет [диалоговое окно «Выбор цвета»](../windows/custom-color-selector-dialog-box-image-editor-for-icons.md) отображается.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Сочетания клавиш](../windows/accelerator-keys-image-editor-for-icons.md)   
 [Значки и курсоры: ресурсы изображений для устройств отображения](../windows/icons-and-cursors-image-resources-for-display-devices-image-editor-for-icons.md)