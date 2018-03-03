---
title: "Способ: измените язык или условие ресурса при копировании | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3655366e8851494482e628b9c260c796df3f64bd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>Практическое руководство. Изменение языка или условий использования ресурса в процессе копирования
Во время копирования ресурса можно изменить его свойство "язык" и (или) "условие".  
  
-   Язык ресурса определяет собственно язык ресурса. Это значение используется [FindResource](http://msdn.microsoft.com/library/windows/desktop/ms648042) для идентификации ресурсов, для которого необходимо найти. (Однако ресурсы могут иметь отличия, характерные для каждого языка, которые не связаны с текстом, например, сочетания клавиш, которые работают только на японской клавиатуре или растровые изображения, подходящие только для китайских локализованных сборок, и т. д.)  
  
-   Условие ресурса — это определенный символ, задающий условие, при котором будет использоваться конкретная копия ресурса.  
  
 Язык и условие ресурса отображаются в окне рабочей области в скобках после имени ресурса. В этом примере ресурс с именем IDD_AboutBox использует финский язык и его условие имеет значение XX33.  
  
```  
IDD_AboutBox (Finnish - XX33)  
```  
  
### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Копирование существующего ресурса и изменение его языка или условия  
  
1.  В RC-файле или в [представление ресурсов](../windows/resource-view-window.md) окно, щелкните правой кнопкой мыши ресурс, который нужно скопировать.  
  
2.  Выберите **вставить копию** в контекстном меню.  
  
3.  В **Вставка копии ресурса** диалоговое окно:  
  
    -   Для **языка** выберите язык.  
  
    -   В **условие** введите условие.  
  

  
 Требования  
  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Как: копирование ресурсов](../windows/how-to-copy-resources.md)   
 [Файлы ресурсов](../windows/resource-files-visual-studio.md)   
 [Редакторы ресурсов](../windows/resource-editors.md)