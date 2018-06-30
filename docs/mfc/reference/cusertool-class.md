---
title: Класс CUserTool | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CUserTool
- AFXUSERTOOL/CUserTool
- AFXUSERTOOL/CUserTool::CopyIconToClipboard
- AFXUSERTOOL/CUserTool::DrawToolIcon
- AFXUSERTOOL/CUserTool::GetCommand
- AFXUSERTOOL/CUserTool::GetCommandId
- AFXUSERTOOL/CUserTool::Invoke
- AFXUSERTOOL/CUserTool::Serialize
- AFXUSERTOOL/CUserTool::SetCommand
- AFXUSERTOOL/CUserTool::SetToolIcon
- AFXUSERTOOL/CUserTool::LoadDefaultIcon
- AFXUSERTOOL/CUserTool::m_strArguments
- AFXUSERTOOL/CUserTool::m_strInitialDirectory
- AFXUSERTOOL/CUserTool::m_strLabel
dev_langs:
- C++
helpviewer_keywords:
- CUserTool [MFC], CopyIconToClipboard
- CUserTool [MFC], DrawToolIcon
- CUserTool [MFC], GetCommand
- CUserTool [MFC], GetCommandId
- CUserTool [MFC], Invoke
- CUserTool [MFC], Serialize
- CUserTool [MFC], SetCommand
- CUserTool [MFC], SetToolIcon
- CUserTool [MFC], LoadDefaultIcon
- CUserTool [MFC], m_strArguments
- CUserTool [MFC], m_strInitialDirectory
- CUserTool [MFC], m_strLabel
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 925e93afae4682497263eb96832aa466c6034231
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121320"
---
# <a name="cusertool-class"></a>Класс CUserTool
Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. **Средства** вкладке **Настройка** диалоговое окно ( [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) позволяет пользователю добавить пользовательские средства и укажите имя, команду, аргументы, и исходный каталог для каждого пользовательского средства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|Рисует значок средства пользователя в заданном прямоугольнике.|  
|[CUserTool::GetCommand](#getcommand)|Возвращает строку, содержащую текст команды, связанные с помощью средства пользователя.|  
|[CUserTool::GetCommandId](#getcommandid)|Возвращает идентификатор команды пункта меню средства пользователя.|  
|[CUserTool::Invoke](#invoke)|Выполняет команду, связанных со средством пользователя.|  
|[CUserTool::Serialize](#serialize)|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CUserTool::SetCommand](#setcommand)|Задает команду, связанную со средством пользователя.|  
|[CUserTool::SetToolIcon](#settoolicon)|Значок для пользовательского средства загружает из приложения, связанного с помощью средства.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Загружает значок по умолчанию для пользовательского средства.|  
  
### <a name="data-members"></a>Элементы данных  
  
|name|Описание:|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|Аргументы командной строки для средства пользователя.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Исходный каталог для пользовательского средства.|  
|[CUserTool::m_strLabel](#m_strlabel)|Имя инструмента, который отображается в элементе меню средства.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о включении средства пользователя в приложении см. в разделе [CUserToolsManager класса](../../mfc/reference/cusertoolsmanager-class.md).  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как создать инструмент из `CUserToolsManager` , задайте `m_strLabel` переменной-члена, а также установите приложение, которое пользователь будет запущена. Этот фрагмент кода является частью [Visual Studio демонстрационный пример](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#35](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxusertool.h  
  
##  <a name="copyicontoclipboard"></a>  CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="drawtoolicon"></a>  CUserTool::DrawToolIcon  
 Рисует значок средства пользователя по центру заданного прямоугольника.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *основного контроллера домена*  
 Указатель на контекст устройства.  
  
 [in] *rectImage*  
 Задает координаты области для отображения значка.  
  
##  <a name="getcommand"></a>  CUserTool::GetCommand  
 Возвращает строку, содержащую текст команды, связанные с помощью средства пользователя.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CString` объект, содержащий текст команды, связанные с помощью средства пользователя.  
  
##  <a name="getcommandid"></a>  CUserTool::GetCommandId  
 Возвращает идентификатор команды пользовательского инструмента.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды этого пользовательского инструмента.  
  
##  <a name="invoke"></a>  CUserTool::Invoke  
 Выполняет команду, связанных со средством пользователя.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данная команда была выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) для выполнения команд, связанных со средством пользователя. Операция завершается ошибкой, если команда является пустым или [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) завершается ошибкой.  
  
##  <a name="loaddefaulticon"></a>  CUserTool::LoadDefaultIcon  
 Загружает значок по умолчанию для пользовательского средства.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор загрузить значок (HICON) или значение NULL, если не удается загрузить значок по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда не удается загрузить значок для определяемый пользователем инструмент из исполняемого файла средства.  
  
 Переопределите этот метод, чтобы предоставить свои собственные средства значок по умолчанию.  
  
##  <a name="m_strarguments"></a>  CUserTool::m_strArguments  
 Аргументы командной строки для средства пользователя.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта строка передается в средство при вызове [CUserTool::Invoke](#invoke) или когда пользователь выбирает команду, связанную с помощью этого средства.  
  
##  <a name="m_strinitialdirectory"></a>  CUserTool::m_strInitialDirectory  
 Задает начальный каталог для пользовательского средства.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная указывает начальный каталог, средство выполняет в при вызове [CUserTool::Invoke](#invoke) или когда пользователь выбирает команду, связанную с помощью этого средства.  
  
##  <a name="m_strlabel"></a>  CUserTool::m_strLabel  
 Надпись, отображаемая в элементе меню программы.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="serialize"></a>  CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *ar*  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcommand"></a>  CUserTool::SetCommand  
 Задает приложение, которое пользователь будет запущена.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] *lpszCmd*  
 Указывает новое приложение, необходимо сопоставить со средством пользователя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для установки нового приложения, которое пользователь будет запущена. Метод уничтожает старый значок и загружает новый значок из данного приложения. Если его не удается загрузить значок из приложения, он загружает значок по умолчанию для пользовательского средства путем вызова [CUserTool::LoadDefaultIcon](#loaddefaulticon).  
  
##  <a name="settoolicon"></a>  CUserTool::SetToolIcon  
 Значок для пользовательского средства загружает из приложения, который используется средством.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор загрузить значок.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для загрузки значка, отображаемого в элементе меню. Этот метод осуществляет поиск значок в исполняемом файле, который используется средством. Если он имеет значок по умолчанию, предоставляемые значок [CUserTool::LoadDefaultIcon](#loaddefaulticon) вместо него будет использоваться.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CWinAppEx](../../mfc/reference/cwinappex-class.md)   
 [Класс CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)
