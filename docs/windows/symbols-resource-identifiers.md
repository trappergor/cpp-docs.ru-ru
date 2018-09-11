---
title: 'Символы: Идентификаторы ресурсов (C++) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.identifiers
dev_langs:
- C++
helpviewer_keywords:
- symbols [C++], resource identifiers
- symbols [C++], creating
- resource symbols
- symbols [C++], editing
- resource editors [C++], resource symbols
ms.assetid: 8fccc09a-0237-4a65-b9c4-57d60c59e324
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a1a0b16ebee0ebac141d5c1675d7ff7560b374b
ms.sourcegitcommit: f0c90000125a9497bf61e41624de189a043703c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/10/2018
ms.locfileid: "44318217"
---
# <a name="symbols-resource-identifiers-c"></a>Символы: Идентификаторы ресурсов (C++)

Символ представляет собой идентификатор ресурса, состоящий из двух частей: текстовой строки (имени символа), сопоставленной с целочисленным значением (значением символа). Пример:

```
IDC_EDITNAME = 5100
```

Под идентификаторами, как правило, подразумевают имена символов.

Символы позволяют описательно ссылаться на ресурсы и объекты пользовательского интерфейса как в исходном коде, так и во время работы с ресурсами в редакторах. Диалоговое окно [Символы ресурсов](../windows/viewing-resource-symbols.md)представляет собой удобный инструмент, позволяющий выполнять с символами разные действия.

В процессе создания ресурса или объекта ресурса [редакторы ресурсов](../windows/resource-editors.md) присваивают ресурсу имя по умолчанию, например `IDC_RADIO1`, а также присваивают ему значение. Определение, состоящее из имени и значения, хранится в файле Resource.h.

> [!NOTE]
> В процессе копирования ресурсов или объектов ресурсов из одного RC-файла в другой Visual C++ может изменить значение или имя и значение символа копируемого ресурса во избежание конфликтов с именами и значениями символов в существующем файле.

Соответственно тому, как увеличивается размер приложения и сложность его структуры, растет количество ресурсов и символов. Отслеживание большого количества символов, разбросанных по нескольким файлам, может оказаться трудоемкой задачей. Диалоговое окно [Символы ресурсов](../windows/resource-symbols-dialog-box.md) упрощает управление символами, позволяя выполнять следующие действия:

- [просмотр символов ресурсов;](../windows/viewing-resource-symbols.md)

- [создание символов;](../windows/creating-new-symbols.md)

- [изменение неназначенных символов;](../windows/changing-unassigned-symbols.md)

- [удаление неназначенных символов;](../windows/deleting-unassigned-symbols.md)

- [открытие редактора ресурсов для заданного символа;](../windows/opening-the-resource-editor-for-a-given-symbol.md)

- [изменение символа или символьного имени (идентификатора);](../windows/changing-a-symbol-or-symbol-name-id.md)

- [изменение числового значения символа;](../windows/changing-a-symbol-s-numeric-value.md)

- [изменение имен файлов заголовков символов;](../windows/changing-the-names-of-symbol-header-files.md)

- [включение общих (доступных только для чтения) или вычисляемых символов;](../windows/including-shared-read-only-or-calculated-symbols.md)

- [просмотр предопределенных идентификаторов символов.](../windows/predefined-symbol-ids.md)

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях, см. в разделе [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Практическое руководство. Поиск символов в ресурсах](../windows/how-to-search-for-symbols-in-resources.md)  
[Редакторы ресурсов](../windows/resource-editors.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)