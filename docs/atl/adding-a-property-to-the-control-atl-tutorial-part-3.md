---
title: "Добавление свойства в элемент управления (ATL учебника, часть 3) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: get-started-article
dev_langs:
- C++
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a316ba56c551d0ee47261160058b00eca5e51a4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="adding-a-property-to-the-control-atl-tutorial-part-3"></a>Добавление свойства в элемент управления (учебник ATL, часть 3)
`IPolyCtl`является интерфейсом, который содержит элемент управления пользовательские методы и свойства, и к нему будет добавлено свойство.  
  
### <a name="to-add-a-property-using-the-add-property-wizard"></a>Чтобы добавить свойство, используя мастер добавления свойства  
  
1.  В представлении класса разверните многоугольника.  
  
2.  Щелкните правой кнопкой мыши IPolyCtl.  
  
3.  В контекстном меню выберите **добавить**, а затем нажмите кнопку **добавить свойство**.  
  
     Появится мастер добавления свойств.  
  
4.  В раскрывающемся списке типов свойств, выберите `SHORT`.  
  
5.  Тип `Sides` как **имя свойства.**  
  
6.  Нажмите кнопку **Готово** чтобы завершить добавление свойства.  
  
 При добавлении свойства к интерфейсу MIDL (программу, которая компилирует IDL-файлы) определяет `Get` метод получения значения и `Put` метод для установки нового значения. Методы именуется путем добавления префикса `put_` и `get_` к имени свойства.  
  
 Мастер добавления свойств добавляет необходимые строки в IDL-файл. Он также добавляет `Get` и `Put` функцией прототипов в определение класса в PolyCtl.h и добавляет пустую реализацию PolyCtl.cpp. Это можно проверить, открыв PolyCtl.cpp и поиске функции `get_Sides` и `put_Sides`.  
  
 Несмотря на то, что имеется каркас функции для задания и получения свойства, ему требуется место для сохранения. Вы создадите переменной для хранения свойства и соответствующим образом обновить функции.  
  
#### <a name="to-create-a-variable-to-store-the-property-and-update-the-put-and-get-methods"></a>Создание переменной для хранения свойства, put и с именами методов get  
  
1.  В обозревателе решений откройте PolyCtl.h и добавьте следующую строку после определения `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  Значение по умолчанию `m_nSides`. Сделать фигуры треугольника, добавьте строку в конструктор в PolyCtl.h по умолчанию:  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  Реализуйте `Get` и `Put` методы. `get_Sides` И `put_Sides` PolyCtl.h были добавлены объявления функций. Замените код в PolyCtl.cpp для `get_Sides` и `put_Sides` следующим кодом:  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/cpp/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 `get_Sides` Метод возвращает текущее значение `Sides` свойства через `pVal` указателя. В `put_Sides` метода в коде обеспечивается параметр пользователя `Sides` свойство допустимым значением. Минимальное значение должно быть 2 и так как массив точек будет использоваться для каждой стороны, 100 является разумные пределы для максимального значения.  
  
 Теперь у вас есть свойство с именем `Sides`. На следующем шаге будет изменить код рисования для его использования.  
  
 [Вернитесь к шагу 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [Шагу 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## <a name="see-also"></a>См. также  
 [Учебник](../atl/active-template-library-atl-tutorial.md)

