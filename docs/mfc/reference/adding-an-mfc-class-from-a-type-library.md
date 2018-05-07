---
title: Добавление класса MFC из библиотеки типов | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- classes [MFC], adding MFC
- MFC, adding classes from type libraries
- type libraries, adding MFC classes from
ms.assetid: aba40476-3cfb-47af-990e-ae2e9e0d79cf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 349d06d7fecb82af64fbf2d3b2ebe54689b3b292
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов
Этот мастер используется для создания класса MFC из интерфейса в доступной библиотеке типов. Можно добавить класс MFC для [приложение MFC](../../mfc/reference/creating-an-mfc-application.md), [MFC DLL](../../mfc/reference/creating-an-mfc-dll-project.md), или [управления MFC ActiveX](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Необходимо создать проект MFC с автоматизацией включить для добавления класса из библиотеки типов.  
  
 Библиотека типов содержит двоичное Описание интерфейсов, предоставляемых компонентом, определяющий методы вместе с параметрами и возвращаемыми типами. Необходимо зарегистрировать свою библиотеку типов для его отображения в **доступные библиотеки типов** списка в мастер добавления классов из Typelib. В разделе «Внутри распределенных COM: тип библиотеки и язык интеграции» в библиотеке MSDN для получения дополнительной информации.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов  
  
1.  В любом **обозревателе решений** или [представление классов](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить класс.  
  
2.  В контекстном меню щелкните **добавить**, а затем нажмите кнопку **Добавление класса**.  
  
3.  В [добавить класс](../../ide/add-class-dialog-box.md) щелкните в области шаблонов диалогового **класс MFC из Typelib**, а затем нажмите кнопку **откройте** для отображения [Typelib мастер добавления классов из ](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 В мастере можно добавить несколько классов из библиотеки типов. Аналогично можно добавлять классы из нескольких библиотек типов в одном сеансе мастера.  
  
 Мастер создает класс MFC, производный от [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), для каждого интерфейса, добавляемого из выбранной библиотеки типов. `COleDispatchDriver` реализует автоматизацию OLE на стороне клиента.  
  
## <a name="see-also"></a>См. также  
 [Клиенты автоматизации](../../mfc/automation-clients.md)   
 [Клиенты автоматизации. Использование библиотек типов](../../mfc/automation-clients-using-type-libraries.md)

