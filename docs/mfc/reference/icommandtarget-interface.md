---
title: "Интерфейс ICommandTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs: C++
helpviewer_keywords: ICommandTarget interface [MFC]
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: "27"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: be8adb388bed39f91637dd1ef37ee1ee895f291d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="icommandtarget-interface"></a>Интерфейс ICommandTarget
Пользовательский элемент управления предоставляет интерфейс для получения команд из исходного объекта команды.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[ICommandTarget::Initialize](#initialize)|Инициализирует целевой объект команды.|  
  
## <a name="remarks"></a>Примечания  
 Если разместить пользовательский элемент управления в представлении MFC [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команды пользовательского интерфейса сообщения в пользовательский элемент управления мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации `ICommandTarget`, вы предоставляете ссылку на пользовательский элемент управления [руководство](../../mfc/reference/icommandsource-interface.md) объекта.  
  
 В разделе [как: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример демонстрирует использование `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h (определенный в сборке atlmfc\lib\mfcmifc80.dll)  
  
##  <a name="initialize"></a>ICommandTarget::Initialize  
 Инициализирует целевой объект команды.  
  
```  
void Initialize(ICommandSource^ cmdSource);  
```  
  
### <a name="parameters"></a>Параметры  
 `cmdSource`  
 Дескриптор исходный объект команды.  
  
### <a name="remarks"></a>Примечания  
 При размещении пользовательских элементов управления представления MFC CWinFormsView направляет команды и сообщения пользовательского интерфейса команд обновления в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC.  
  
 Этот метод инициализирует целевой объект команды и связывает его с cmdSource указанную команду исходного объекта. Он должен вызываться в реализацию класса пользовательского элемента управления. При инициализации следует зарегистрировать обработчики команд с исходным объектом команды путем вызова ICommandSource::AddCommandHandler в реализации Initialize. В разделе как: Добавление элемента управления Windows Forms в качестве примера использования инициализации для этого маршрутизация команд.  
  
## <a name="see-also"></a>См. также  
 [Как: Добавление команды управления маршрутизации в Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [Интерфейс ICommandSource](../../mfc/reference/icommandsource-interface.md)



