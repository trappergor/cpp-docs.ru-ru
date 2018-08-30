---
title: Создание новых символов | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
f1_keywords:
- vc.editors.symbol.creating
dev_langs:
- C++
helpviewer_keywords:
- New Symbol dialog box
- symbols, creating
ms.assetid: 35168d31-3af6-4ecd-9362-3707d47b53f3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9d84eef4c91442eedc830fdee836dc5d950b5eae
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43209594"
---
# <a name="creating-new-symbols"></a>Создание новых символов

В начале работы над новым проектом может оказаться удобным спланировать необходимые имена символов перед созданием ресурсов, которым они будут назначены.

### <a name="to-create-a-new-symbol-using-the-resource-symbols-dialog-box"></a>Создание нового символа с помощью диалогового окна символов ресурсов

1. В [символы ресурсов-диалоговое окно](../windows/resource-symbols-dialog-box.md), выберите **New**.

2. В **имя** введите имя символа.

3. Оставьте предложенное значение.

   - или -

   В **значение** введите новое значение.

4. Нажмите кнопку **ОК** для добавления нового символа в список символов.

Если будет введено имя символа, которое уже существует, появится сообщение о том, что символ с таким именем уже определен. Нельзя определить два и несколько символов с одинаковыми именами, но можно определить разные символы с одинаковыми числовыми значениями. Дополнительные сведения см. в разделе [ограничения для имен символов](../windows/symbol-name-restrictions.md) и [ограничения для значений символов](../windows/symbol-value-restrictions.md).

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам отображать статические ресурсы и назначение ресурсов строки свойства.

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Просмотр символов ресурсов](../windows/viewing-resource-symbols.md)  
[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)