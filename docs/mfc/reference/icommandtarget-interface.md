---
title: "Интерфейс ICommandTarget | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ICommandTarget
- AFXWINFORMS/ICommandTarget
- AFXWINFORMS/ICommandTarget::Initialize
dev_langs:
- C++
helpviewer_keywords:
- ICommandTarget interface
ms.assetid: dd9927f6-3479-4e7c-8ef9-13206cf901f3
caps.latest.revision: 27
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 825fde18c56afb91bdb469212817109dc35abf68
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="icommandtarget-interface"></a>Интерфейс ICommandTarget
Предоставляет интерфейс для получения команд из исходного объекта команды пользовательского элемента управления.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
interface class ICommandTarget  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[ICommandTarget::Initialize](#initialize)|Инициализирует целевой объект команды.|  
  
## <a name="remarks"></a>Примечания  
 При размещении пользовательских элементов управления представления MFC, [CWinFormsView](../../mfc/reference/cwinformsview-class.md) команды маршруты и обновление команду сообщения пользовательского интерфейса в пользовательский элемент управления, чтобы тот мог обрабатывать команды MFC (например, элементы меню и кнопки панели инструментов). Путем реализации `ICommandTarget`, предоставить ссылку на пользовательский элемент управления [ICommandSource](../../mfc/reference/icommandsource-interface.md) объекта.  
  
 В разделе [Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md) пример использования `ICommandTarget`.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
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
  
 Этот метод инициализирует целевой объект команды и связывает его с cmdSource указанную команду исходного объекта. Он должен быть вызван в реализацию класса пользовательского элемента управления. При инициализации необходимо зарегистрировать обработчики команд в исходный объект команды, вызывающей ICommandSource::AddCommandHandler в реализации инициализации. В разделе Практическое руководство: Добавление маршрутизации команд для элемента управления Windows Forms для использования инициализации для этого примера.  
  
## <a name="see-also"></a>См. также  
 [Практическое руководство: Добавление команды управления маршрутизации в Windows Forms](../../dotnet/how-to-add-command-routing-to-the-windows-forms-control.md)   
 [Интерфейс ICommandSource](../../mfc/reference/icommandsource-interface.md)




