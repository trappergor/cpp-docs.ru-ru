---
title: 'Практическое: изменение языка или условий использования ресурса в процессе копирования | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.resvw.resource.changing
dev_langs:
- C++
helpviewer_keywords:
- Language property
- condition property of resource
ms.assetid: 8f622ab0-bac2-468f-ae70-78911afc4759
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a4acb718d44a5abcf4413cbb7f026e4a8ea0f57b
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43218093"
---
# <a name="how-to-change-the-language-or-condition-of-a-resource-while-copying"></a>Практическое руководство. Изменение языка или условий использования ресурса в процессе копирования

Во время копирования ресурса можно изменить его свойство "язык" и (или) "условие".

- Язык ресурса определяет собственно язык ресурса. Это значение используется [FindResource](/windows/desktop/api/winbase/nf-winbase-findresourcea) для идентификации ресурсов, для которого вам нужен. (Однако ресурсы могут иметь отличия, характерные для каждого языка, которые не связаны с текстом, например, сочетания клавиш, которые работают только на японской клавиатуре или растровые изображения, подходящие только для китайских локализованных сборок, и т. д.)

- Условие ресурса — это определенный символ, задающий условие, при котором будет использоваться конкретная копия ресурса.

Язык и условие ресурса отображаются в окне рабочей области в скобках после имени ресурса. В этом примере ресурс с именем IDD_AboutBox использует финский язык и его условие имеет значение XX33.

```cpp
IDD_AboutBox (Finnish - XX33)  
```

### <a name="to-copy-an-existing-resource-and-change-its-language-or-condition"></a>Копирование существующего ресурса и изменение его языка или условия

1. В RC-файле или в [представление ресурсов](../windows/resource-view-window.md) окно, щелкните правой кнопкой мыши ресурс, который требуется скопировать.

2. Выберите **вставить копию** в контекстном меню.

3. В **Вставка копии ресурса** диалоговое окно:

   - Для **языка** выберите язык.

   - В **условие** введите условие.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Практическое руководство. Копирование ресурсов](../windows/how-to-copy-resources.md)  
[Файлы ресурсов](../windows/resource-files-visual-studio.md)  
[Редакторы ресурсов](../windows/resource-editors.md)