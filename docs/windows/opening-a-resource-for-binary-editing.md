---
title: "Открытие ресурса для редактирования в двоичном редакторе | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.editors.binary
dev_langs: C++
helpviewer_keywords:
- binary data, editing
- resources [Visual Studio], opening for binary editing
ms.assetid: d3cdb0e4-da66-410d-8e49-b29073ff2929
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92a0c0459626f139b7a8d7ae2313439c66d2a11c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="opening-a-resource-for-binary-editing"></a>Открытие ресурса для редактирования в двоичном редакторе
### <a name="to-open-a-windows-desktop-resource-for-binary-editing"></a>Открытие ресурса классического приложения Windows для редактирования в двоичном редакторе  
  
1.  В окне [представления ресурсов](../windows/resource-view-window.md)выберите файл ресурсов, который необходимо изменить.  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  Щелкните ресурс правой кнопкой мыши, а затем выберите в контекстном меню команду **Открыть двоичные данные** .  
  
    > [!NOTE]
    >  Если с помощью окна [представления ресурсов](../windows/resource-view-window.md) открыть ресурс, формат которого не распознается средой Visual Studio (например, RCDATA или настраиваемый ресурс), ресурс будет автоматически открыт в двоичном редакторе.  
  
### <a name="to-open-a-managed-resource-for-binary-editing"></a>Открытие управляемого ресурса для редактирования в двоичном редакторе  
  
1.  В обозревателе решений выберите файл ресурсов, который необходимо изменить.  
  
2.  Щелкните ресурс правой кнопкой мыши, а затем выберите в контекстном меню команду **Открыть с помощью** .  
  
3.  В диалоговом окне **Открыть с помощью** выберите **Двоичный редактор**.  
  
    > [!NOTE]
    >  Для работы с файлами ресурсов в управляемых проектах можно использовать [редактор изображений](../windows/image-editor-for-icons.md) и [двоичный редактор](binary-editor.md) . Все управляемые ресурсы, которые нужно редактировать, должны быть связанными ресурсами. Редакторы ресурсов Visual Studio не поддерживают редактирование внедренных ресурсов.  
  
    > [!NOTE]
    >  Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).   
  
 ![Двоичный редактор](../mfc/media/vcbinaryeditor2.gif "vcBinaryEditor2")  
Двоичные данные диалогового окна в двоичном редакторе  
  
 Только некоторые значение ASCII могут быть представлены в двоичном редакторе (в диапазоне от 0x20 до 0x7E). Дополнительные символы отображаются в виде точек в разделе "Значение ASCII" (на правой панели двоичного редактора). "Печатным" символам соответствуют значения ASCII в диапазоне от 32 до 126.  
  
> [!NOTE]
>  Если с помощью двоичного редактора необходимо отредактировать ресурс, который открыт в другом редакторе, необходимо сначала закрыть другой редактор.  
  
 **Требования**  
  
 Нет  
  
## <a name="see-also"></a>См. также  
 [Binary Editor](binary-editor.md)

