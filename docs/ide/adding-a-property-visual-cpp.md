---
title: Добавление свойства (Visual C++) | Документы Microsoft
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
ms.openlocfilehash: 45eda098202fdf9286905bdc967b6aa1d7bd7035
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="adding-a-property-visual-c"></a>Добавление свойства (Visual C++)
Можно использовать [мастер добавления свойств](../ide/names-add-property-wizard.md) Чтобы добавить метод в интерфейс в проекте.  
  
### <a name="to-add-a-property-to-your-object"></a>Чтобы добавить свойство в объект  
  
1.  В [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя интерфейса, к которому требуется добавить свойство.  
  
    > [!NOTE]
    >  Можно также добавлять свойства к диспетчерских, что, если проект имеет атрибуты, вложенные в узле библиотеки.  
  
2.  В контекстном меню щелкните **добавить**, а затем нажмите кнопку **добавить свойство**.  
  
3.  В [мастер добавления свойств](../ide/names-add-property-wizard.md), укажите сведения для создания свойства.  
  
4.  Задайте параметры языка (IDL) определение свойства в [атрибуты IDL](../ide/idl-attributes-add-property-wizard.md) странице мастера.  
  
5.  Нажмите кнопку **Готово** для добавления свойств.  
  
 **Получить** и `Put` методы свойства отображаются в виде двух значков в представлении классов под интерфейсом, в которой она определена. Можно дважды щелкнуть любой значок, чтобы просмотреть объявление свойства в IDL-файл.  
  
-   Для интерфейсов ATL **получить** и **поместить** функции добавляются в CPP-файл, а ссылки на эти функции будут добавлены в h-файл.  
  
-   Для диспетчера интерфейсов MFC, при выборе **переменной-члена** как тип реализации метод и переменная добавляются в класс, который его реализует. При выборе **методы Get и Set** как тип реализации будет добавлено два метода в класс, который его реализует.  
  
## <a name="see-also"></a>См. также  
 [Создание интерфейса COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Редактирование интерфейса COM](../ide/editing-a-com-interface.md)   
 [Модель COM](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [Указатели интерфейса и интерфейсы](http://msdn.microsoft.com/library/windows/desktop/ms688484)