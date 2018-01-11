---
title: "Переопределение виртуальной функции (Visual C++) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.virtualfunc.override
dev_langs: C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 98e77579d511f4c78f0f7835c0b3c1dcea632734
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="overriding-a-virtual-function-visual-c"></a>Переопределение виртуальной функции (Visual C++)
Можно переопределить виртуальные функции, определенные в базовом классе из Visual Studio [окно свойств](/visualstudio/ide/reference/properties-window).  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Переопределение виртуальной функции в окне «Свойства»  
  
1.  В представлении классов щелкните требуемый класс.  
  
2.  В окне «Свойства» щелкните **переопределяет** кнопки.  
  
    > [!NOTE]
    >  **Переопределяет** кнопка доступна при выборе имени класса в представлении классов или при нажатии кнопки в окне исходного кода.  
  
     В левой столбце перечислены виртуальные функции. Если имя виртуальной функции также отображается в правом столбце, затем переопределения уже была реализована.  
  
3.  Если функция не имеет переопределения, затем щелкните ячейку в правом столбце в окне «Свойства», чтобы отобразить предлагаемое имя функции, переопределяют \<Добавить >*FuncName*.  
  
4.  Щелкните предлагаемое имя, чтобы добавить код заглушки для функции.  
  
5.  Чтобы изменить переопределяющую функцию, дважды щелкните имя функции в представлении классов и редактировать код в окне исходного кода.  
  
 Чтобы удалить переопределение, щелкните имя переопределяющей функции в правом столбце и выберите \<удалить >*FuncName*. Код функции комментарий.  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../ide/navigating-the-class-structure-visual-cpp.md)