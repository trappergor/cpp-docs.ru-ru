---
title: Редактор сочетаний клавиш | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.accelerator.F1
dev_langs:
- C++
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [Visual Studio], accelerator key
- accelerator keys
- resource editors, Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
- Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: feece642928db70a2b78dd3a4117b695b19f4af9
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466076"
---
# <a name="accelerator-editor"></a>Редактор сочетаний клавиш
Таблица сочетаний клавиш представляет собой ресурс Windows, содержащий список сочетаний клавиш и связанных с ними идентификаторов команд. В программе можно использовать несколько таблиц сочетаний клавиш.  
  
 Обычно сочетания клавиш используются для ускорения доступа к командам программы, также доступным в меню или на панели инструментов. Но таблицу сочетаний клавиш можно также использовать, чтобы определить сочетания клавиш для команд, с которыми не связаны никакие объекты пользовательского интерфейса.  
  
 Можно использовать [представление классов](http://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) для подключения команд сочетаний клавиш к коду.  
  
 Редактор сочетаний клавиш позволяет выполнять следующие действия:  
  
-   [задавать свойства сочетаний клавиш;](../windows/setting-accelerator-properties.md)  
  
-   [привязывать сочетания клавиш к пунктам меню;](../windows/associating-an-accelerator-key-with-a-menu-item.md)  
  
-   [редактировать таблицы сочетаний клавиш;](../windows/editing-accelerator-tables.md)  
  
-   [использовать предопределенные сочетания клавиш.](../windows/predefined-accelerator-keys.md)  
  
    > [!TIP]
    >  При использовании редактора сочетаний клавиш можно щелкнуть правой кнопкой мыши, чтобы вывести контекстное меню с часто используемыми командами. Доступные команды зависят от объекта, на который наведен указатель мыши.  
  
    > [!NOTE]
    >  Операционная система Windows не позволяет создавать пустые таблицы сочетаний клавиш. Если вы создадите таблицу сочетаний клавиш, не содержащую записей, она будет автоматически удалена при сохранении.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).  
  
## <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Редакторы ресурсов](../windows/resource-editors.md)