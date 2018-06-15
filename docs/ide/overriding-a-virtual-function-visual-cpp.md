---
title: Переопределение виртуальной функции (Visual C++) | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.virtualfunc.override
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, overriding
- base classes, overriding virtual functions defined in
- Properties window, overriding virtual functions in
ms.assetid: 2d8c76f2-7a6b-4c9c-8de5-4282ce7755b6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d8580d27442b0cae7e343a568beaa9aeae500461
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33337747"
---
# <a name="overriding-a-virtual-function-visual-c"></a>Переопределение виртуальной функции (Visual C++)
Вы можете переопределить виртуальные функции, определенные в базовом классе, из [окна "Свойства"](/visualstudio/ide/reference/properties-window) Visual Studio.  
  
### <a name="to-override-a-virtual-function-in-the-properties-window"></a>Переопределение виртуальной функции в окне "Свойства"  
  
1.  Щелкните класс в представлении классов.  
  
2.  В окне "Свойства" нажмите кнопку **Переопределение**.  
  
    > [!NOTE]
    >  Кнопка **Переопределение** доступна, когда вы выбираете имя класса в представлении классов или щелкаете внутри исходного окна.  
  
     В левом столбце перечислены виртуальные функции. Если имя виртуальной функции также отображается в правом столбце, значит, переопределение уже было реализовано.  
  
3.  Если функция не имеет переопределения, щелкните ячейку в правом столбце в окне "Свойства", чтобы отобразить предлагаемое имя переопределения функции в виде \<add>*имя_функции*.  
  
4.  Щелкните предлагаемое имя, чтобы добавить код заглушки для функции.  
  
5.  Чтобы изменить переопределяющую функцию, дважды щелкните ее имя в представлении классов и измените код в исходном окне.  
  
 Чтобы удалить переопределение, щелкните имя переопределяющей функции в правом столбце и выберите \<delete>*имя_функции*. Код функции закомментируется.  
  
## <a name="see-also"></a>См. также  
 [Добавление функциональных возможностей с помощью мастеров кода](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Добавление класса](../ide/adding-a-class-visual-cpp.md)   
 [Добавление функции-члена](../ide/adding-a-member-function-visual-cpp.md)   
 [Добавление переменной-члена](../ide/adding-a-member-variable-visual-cpp.md)   
 [Обработчик сообщений MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Перемещение по структуре класса](../ide/navigating-the-class-structure-visual-cpp.md)