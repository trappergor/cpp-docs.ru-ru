---
title: "Редактор сведений о версии | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.editors.version.F1
dev_langs:
- C++
helpviewer_keywords:
- Version Information editor, about Version Information editor
- editors, Version Information
- resource editors, Version Information editor
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7c221120bf7170025506fe49fe2ab6419ce66044
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="version-information-editor"></a>Редактор сведений о версии
Сведения о версии включают идентификационные данные о компании и продукте, номер версии продукта и уведомление об авторских правах и товарных знаках. С помощью редактора сведений о версии можно создавать и поддерживать эти данные, которые хранятся в ресурсе сведений о версии. Ресурс сведений о версии не является обязательным для приложения, но он удобен для сбора сведений, позволяющих идентифицировать приложение. Сведения о версии также используются API-интерфейсами настройки.  
  
 Ресурс сведений о версии содержит верхний блок и один или несколько нижних блоков: один блок фиксированных сведений вверху и один или несколько блоков сведений о версии внизу (для других языков или кодировок). Верхний блок содержит как редактируемые числовые поля, так и раскрывающиеся списки с вариантами для выбора. Нижние блоки содержат только редактируемые текстовые поля.  
  
> [!NOTE]
>  Стандарт Windows разрешает наличие только одного ресурса сведений о версии, который называется VS_VERSION_INFO.  
  
 Редактор сведений о версии позволяет делать следующее:  
  
-   [изменять строку в ресурсе сведений о версии;](../windows/editing-a-string-in-a-version-information-resource.md)  
  
-   [добавлять сведения о версии для другого языка (новый блок сведений о версии);](../windows/adding-version-information-for-another-language.md)  
  
-   [удалять блок сведений о версии;](../windows/deleting-a-version-information-block.md)  
  
-   [получать доступ к сведениям о версии из создаваемой программы.](../windows/accessing-version-information-from-within-your-program.md)  
  
    > [!NOTE]
    >  При использовании редактора сведений о версии во многих случаях можно щелкнуть правой кнопкой мыши, чтобы открыть контекстное меню связанных с ресурсом команд. Например, если щелкнуть, когда указатель находится на заголовке блока, контекстное меню будет содержать команды "Создать блок сведений о версии" и "Удалить блок сведений о версии".  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редакторы ресурсов](../windows/resource-editors.md)   
 [Меню и другие ресурсы](http://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)

