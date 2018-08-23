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
ms.openlocfilehash: 4d1911a8bd8a7f3079497ec66ea1de59aff480a0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42604054"
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

Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в приложениях для настольных систем](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework*. . Сведения о том, как вручную добавлять файлы ресурсов в проекты управляемого кода, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам, см. в разделе [Walkthrough: Using Resources for Localization with ASP.NET](http://msdn.microsoft.com/Library/bb4e5b44-e2b0-48ab-bbe9-609fb33900b6).

## <a name="requirements"></a>Требования

Win32

## <a name="see-also"></a>См. также

[Просмотр символов ресурсов](../windows/viewing-resource-symbols.md)  
[Стандартные идентификаторы символов](../windows/predefined-symbol-ids.md)