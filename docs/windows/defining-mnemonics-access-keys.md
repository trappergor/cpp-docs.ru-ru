---
title: Определение клавиш доступа | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- access keys [C++], adding
- keyboard shortcuts [C++], controls
- dialog box controls, mnemonics
- access keys [C++], checking
- mnemonics, checking for duplicate
- mnemonics
- mnemonics, dialog box controls
- keyboard shortcuts [C++], uniqueness checking
- Check Mnemonics command
- controls [C++], access keys
- access keys [C++]
ms.assetid: 60a85435-aa30-4c5c-98b6-42fb045b9eb2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a60cf597a88fcf7038848be6c9e2d31269f6a906
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873697"
---
# <a name="defining-mnemonics-access-keys"></a>Определение клавиш доступа
Как правило клавиатура перемещение фокуса ввода с одного элемента управления к другому в диалоговом окне, с TAB и клавиш со стрелками. Тем не менее можно определить ключ доступа (сокращение или легко запомнить имя), позволяющий пользователям выбрать элемент управления, нажав клавишу с одним ключом.  
  
### <a name="to-define-an-access-key-for-a-control-with-a-visible-caption-push-buttons-check-boxes-and-radio-buttons"></a>Чтобы определить клавишу доступа для элемента управления в видимом заголовке (кнопки, флажки и переключатели)  
  
1.  Выберите элемент управления в диалоговом окне.  
  
2.  В [окно свойств](/visualstudio/ide/reference/properties-window)в **заголовок** свойство, введите новое имя для элемента управления, введя амперсанд (**&**) перед буквой, как ключ доступа для этого элемента управления. Например, `&Radio1`.  
  
3.  Нажмите клавишу **ВВОД**.  
  
     Подчеркивание появляется в отображаемом заголовке, чтобы указать клавишу доступа, например, **R**adio1.  
  
### <a name="to-define-an-access-key-for-a-control-without-a-visible-caption"></a>Чтобы определить клавишу доступа для элемента управления без видимого заголовка  
  
1.  Создайте заголовок для элемента управления с помощью **статический текст** управления [элементов](/visualstudio/ide/reference/toolbox).  
  
2.  В заголовке статического текста введите амперсанд (**&**) перед буквой, как клавиша доступа.  
  
3.  Убедитесь, что элемент управления надпись непосредственно предшествующий элемент управления, который его метки в последовательности табуляции.  
  
 Все клавиши быстрого доступа в диалоговое окно должно быть уникальным.  
  
#### <a name="to-check-for-duplicate-access-keys"></a>Для проверки дублирующиеся клавиши доступа  
  
1.  На **формат** меню, нажмите кнопку **проверка назначенных клавиш**.  
  
 Сведения о добавлении ресурсов в управляемые проекты см. в разделе [ресурсы в классических приложениях](/dotnet/framework/resources/index) в *руководства разработчика .NET Framework.* Сведения о вручную добавлять файлы ресурсов в управляемые проекты, осуществлять доступ к ресурсам, отображать статические ресурсы и присваивать строки ресурсов свойствам см. в разделе [Создание файлов ресурсов для приложений рабочего стола](/dotnet/framework/resources/creating-resource-files-for-desktop-apps). Сведения о глобализации и локализации ресурсов в управляемых приложениях см. в разделе [Globalizing и локализация приложений .NET Framework](/dotnet/standard/globalization-localization/index).  
  
### <a name="requirements"></a>Требования  
 Win32  
  
## <a name="see-also"></a>См. также  
 [Элементы управления в диалоговых окнах](../windows/controls-in-dialog-boxes.md)   
 [Элементы управления](../mfc/controls-mfc.md)

