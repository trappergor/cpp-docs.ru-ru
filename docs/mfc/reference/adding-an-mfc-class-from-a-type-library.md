---
title: Добавление класса MFC из библиотеки типов | Документация Майкрософт
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
ms.openlocfilehash: 656d5c357874a7b470eb2fd630c91ad0aefa5a0d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43205377"
---
# <a name="adding-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов
Этот мастер используется для создания класса MFC из интерфейса в доступной библиотеке типов. Вы можете добавить класс MFC для [приложения MFC](../../mfc/reference/creating-an-mfc-application.md), [библиотеки DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md) или [элемента управления ActiveX MFC](../../mfc/reference/creating-an-mfc-activex-control.md).  
  
> [!NOTE]
>  Необходимо создать проект MFC с помощью службы автоматизации, возможность добавления классов из библиотеки типов.  
  
 Библиотека типов содержит двоичное Описание интерфейсов, предоставляемых компонентом, определяющий методы, а также их параметры и возвращаемые типы. Библиотека типов должны регистрироваться, чтобы он появился в **доступные библиотеки типов** списка в мастер добавления классов из библиотеки типов. См. в разделе «Внутри распределенных COM: тип библиотеки и язык интеграция» в библиотеке MSDN, Дополнительные сведения.  
  
### <a name="to-add-an-mfc-class-from-a-type-library"></a>Добавление класса MFC из библиотеки типов  
  
1.  В любом **обозревателе решений** или [представление классов](https://msdn.microsoft.com/8d7430a9-3e33-454c-a9e1-a85e3d2db925), щелкните правой кнопкой мыши имя проекта, к которому вы хотите добавить класс.  
  
2.  В контекстном меню выберите команду **Добавить**, а затем — **Добавить класс**.  
  
3.  В [Добавление класса](../../ide/add-class-dialog-box.md) диалоговое окно, в области «Шаблоны» щелкните **класс MFC из Typelib**, а затем нажмите кнопку **откройте** для отображения [Typelib мастер добавления классов из ](../../mfc/reference/add-class-from-typelib-wizard.md).  
  
 В мастере можно добавить более одного класса в библиотеку типов. Аналогичным образом можно добавить классы из более чем одной библиотеки типов в одном сеансе мастера.  
  
 Мастер создает класс MFC, производный от [COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md), для каждого интерфейса, добавленные из выбранной библиотеки типов. `COleDispatchDriver` реализует автоматизацию OLE на стороне клиента.  
  
## <a name="see-also"></a>См. также  
 [Клиенты автоматизации](../../mfc/automation-clients.md)   
 [Клиенты автоматизации. Использование библиотек типов](../../mfc/automation-clients-using-type-libraries.md)

