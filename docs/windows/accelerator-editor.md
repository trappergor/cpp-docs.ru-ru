---
title: Редактор сочетаний клавиш (C++)
ms.date: 11/04/2016
f1_keywords:
- vc.editors.accelerator.F1
helpviewer_keywords:
- accelerator tables [C++], editing
- tables [C++], accelerator key
- accelerator keys [C++]
- resource editors [C++], Accelerator editor
- keyboard shortcuts [C++], Accelerator editor
ms.assetid: 013c30b6-5d61-4f1c-acef-8bd15bed7060
ms.openlocfilehash: fdb2d9cf0954142da990a0a9f995cb482060345d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50621498"
---
# <a name="accelerator-editor-c"></a>Редактор сочетаний клавиш (C++)

Таблицы сочетаний клавиш — это ресурс Windows на C++, который содержит список сочетаний клавиш (также известный как сочетания клавиш) и связанные с ними идентификаторов команд. В программе можно использовать несколько таблиц сочетаний клавиш.

Обычно сочетания клавиш используются для ускорения доступа к командам программы, также доступным в меню или на панели инструментов. Но таблицу сочетаний клавиш можно также использовать, чтобы определить сочетания клавиш для команд, с которыми не связаны никакие объекты пользовательского интерфейса.

Для подключения команд сочетаний клавиш к коду можно использовать [представление классов](/visualstudio/ide/viewing-the-structure-of-code) .

С помощью **Accelerator** редактор, вы можете:

- [задавать свойства сочетаний клавиш;](../windows/setting-accelerator-properties.md)

- [привязывать сочетания клавиш к пунктам меню;](../windows/associating-an-accelerator-key-with-a-menu-item.md)

- [редактировать таблицы сочетаний клавиш;](../windows/editing-accelerator-tables.md)

- [использовать предопределенные сочетания клавиш.](../windows/predefined-accelerator-keys.md)

   > [!TIP]
   > При использовании **Accelerator** редактора, можно щелкнуть правой кнопкой мыши, чтобы вывести контекстное меню с часто используемыми командами. Доступные команды зависят от объекта, на который наведен указатель мыши.

   > [!NOTE]
   > Операционная система Windows не позволяет создавать пустые таблицы сочетаний клавиш. Если вы создадите таблицу сочетаний клавиш, не содержащую записей, она будет автоматически удалена при сохранении.

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Редакторы ресурсов](../windows/resource-editors.md)