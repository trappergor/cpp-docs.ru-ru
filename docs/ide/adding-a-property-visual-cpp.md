---
title: Добавление свойства (Visual C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- interfaces, adding properties
- properties [C++], adding to interfaces
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00b19fa7166e6edad05d729c5a738a2a827086ae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43212799"
---
# <a name="adding-a-property-visual-c"></a>Добавление свойства (Visual C++)
Вы можете использовать [мастер добавления свойства](../ide/names-add-property-wizard.md) для добавления свойства в интерфейс в проекте.  
  
### <a name="to-add-a-property-to-your-object"></a>Добавление свойства в объект  
  
1.  В [представлении классов](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925) щелкните правой кнопкой мыши имя интерфейса, в который нужно добавить свойство.  
  
    > [!NOTE]
    >  Вы также можете добавлять свойства в disp-интерфейсы, которые, если только проект не имеет атрибуты, вложены в узел библиотеки.  
  
2.  В контекстном меню выберите команду **Добавить**, а затем — **Добавить свойство**.  
  
3.  В [мастере добавления свойства](../ide/names-add-property-wizard.md) укажите сведения для создания свойства.  
  
4.  Задайте параметры IDL для этого свойства на странице [Атрибуты IDL](../ide/idl-attributes-add-property-wizard.md) мастера.  
  
5.  Нажмите кнопку **Готово**, чтобы добавить свойство.  
  
 Методы **Get** и `Put` свойства отображаются в представлении классов в виде двух значков под интерфейсом, в котором оно определено. Можно дважды щелкнуть любой значок, чтобы просмотреть объявление свойства в IDL-файле.  
  
-   Для интерфейсов ATL функции **Get** и **Put** добавляются в CPP-файл, а ссылки на эти функции — в H-файл.  
  
-   Для disp-интерфейсов MFC, если выбран тип реализации **Переменная-член**, метод и переменная добавляются в класс, который его реализует. Если выбрать **методы Get/Set** в качестве типа реализации, два метода добавляются в класс, который его реализует.  
  
## <a name="see-also"></a>См. также  
 [Создание интерфейса COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Редактирование интерфейса COM](../ide/editing-a-com-interface.md)   
 [Модель COM](/windows/desktop/com/the-component-object-model)   
 [Указатели интерфейса и интерфейсы](/windows/desktop/com/interface-pointers-and-interfaces)