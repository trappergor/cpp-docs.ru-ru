---
title: "Элементы управления ActiveX MFC: Добавление стандартных методов | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], stock methods
- MFC ActiveX controls [MFC], methods
- DoClick method [MFC]
ms.assetid: bc4fad78-cabd-4cc0-a798-464b1a682f0b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2531f84974626fcdb364df67b12f27d61e75a62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-activex-controls-adding-stock-methods"></a>Элементы управления ActiveX в MFC. Добавление стандартных методов
Стандартный метод отличается от пользовательского метода в том, что уже реализован классом [COleControl](../mfc/reference/colecontrol-class.md). Например `COleControl` содержит функцию стандартных элементов, которая поддерживает метод обновления для элемента управления. Запись карты распределения для этого метод **DISP_STOCKFUNC_REFRESH**.  
  
 `COleControl`поддерживает два стандартных методов: DoClick и обновления. Обновления вызывается пользователем элемента управления, чтобы немедленно обновить внешний вид элемента управления. Срабатывание Click элемента управления вызывается DoClick событий.  
  
|Метод|Элемент карты распределения|Комментарий|  
|------------|------------------------|-------------|  
|`DoClick`|**(DISP_STOCKPROP_DOCLICK)**|Запускает событие Click.|  
|**Обновление**|**(DISP_STOCKPROP_REFRESH)**|Немедленное обновление внешнего вида элемента управления.|  
  
##  <a name="_core_adding_a_stock_method_using_classwizard"></a>Метод, используя мастер добавления метода  
 Добавление стандартных методов является простым с использованием [мастер добавления метода](../ide/add-method-wizard.md). Ниже показано, как добавить метод обновления для элемента управления, созданных с помощью мастера элементов управления ActiveX MFC.  
  
#### <a name="to-add-the-stock-refresh-method-using-the-add-method-wizard"></a>Для добавления стандартных метода обновления, используя мастер добавления метода  
  
1.  Загрузите проект элемента управления.  
  
2.  В представлении класса разверните узел библиотеки элемента управления.  
  
3.  Щелкните правой кнопкой мыши узел интерфейса для элемента управления (второй узел узла библиотеки), чтобы открыть контекстное меню.  
  
4.  В контекстном меню щелкните **добавить** и нажмите кнопку **добавить метод**.  
  
     Откроется мастер добавления метода.  
  
5.  В **имя метода** щелкните **обновление**.  
  
6.  Нажмите кнопку **Готово**.  
  
##  <a name="_core_classwizard_changes_for_stock_methods"></a>Добавьте метод мастер изменения для стандартных методов  
 Так как биржевые метод обновления поддерживается в базовый класс элемента управления, **мастер добавления метода** не изменяет объявление класса элемента управления каким-либо образом. Он добавляет запись для метода в карту диспетчеризации элемента управления и в его. IDL-файл. Следующая строка добавляется в карту диспетчеризации элемента управления, расположенных в его реализации (. Файл .cpp):  
  
 [!code-cpp[NVC_MFC_AxUI#16](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_1.cpp)]  
  
 Это делает доступными метод обновления пользователям элемента управления.  
  
 Следующая строка добавляется к элементу управления. IDL-файла:  
  
 [!code-cpp[NVC_MFC_AxUI#17](../mfc/codesnippet/cpp/mfc-activex-controls-adding-stock-methods_2.idl)]  
  
 Эта строка назначает метод обновления с определенным номером идентификатора.  
  
## <a name="see-also"></a>См. также  
 [Элементы ActiveX библиотеки MFC](../mfc/mfc-activex-controls.md)

