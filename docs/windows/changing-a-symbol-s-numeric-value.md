---
title: Изменение символа&#39;числовое значение s | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.changing.value
dev_langs:
- C++
helpviewer_keywords:
- numeric values
- symbols, numeric values
- numeric values, changing symbols
ms.assetid: 468e903b-9c07-4251-ae09-3b6cb754cc2b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8beacf5195e108d98a0004fe79c2a66cb2b3b610
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="changing-a-symbol39s-numeric-value"></a>Изменение символа&#39;s числовое значение
Для символов, связанных с одним ресурсом, можно использовать [окно "Свойства"](/visualstudio/ide/reference/properties-window) Чтобы изменить значение символа. Можно использовать [символы ресурсов-диалоговое окно](../windows/resource-symbols-dialog-box.md) для изменения значения символов, в данный момент не назначенных ресурсу. Дополнительные сведения см. в разделе [изменение неназначенных символов](../windows/changing-unassigned-symbols.md).  
  
### <a name="to-change-a-symbol-value-assigned-to-a-single-resource-or-object"></a>Изменение значения символа, назначенного одному ресурсу или объекту  
  
1.  В [представление ресурсов](../windows/resource-view-window.md), выберите ресурс.  
  
    > [!NOTE]
    >  Если в проекте еще нет RC-файла, см. раздел [Создание нового файла описания ресурсов](../windows/how-to-create-a-resource-script-file.md).  
  
2.  В **свойства** введите имя символа следуют знак равенства и целое число в **идентификатор** поле, например:  
  
    ```  
    IDC_EDITNAME=5100  
    ```  
  
 Новое значение будет сохранено в файле символов заголовков при очередном сохранении проекта. В поле "Идентификатор" будет отображаться только имя символа. Знак равенства и значение не будут отображаться после проверки.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).  
  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Ограничения для значений символов](../windows/symbol-value-restrictions.md)   
 [Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)