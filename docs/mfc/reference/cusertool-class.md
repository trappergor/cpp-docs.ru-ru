---
title: "Класс CUserTool | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
- CUserTool class
ms.assetid: 7c287d3e-d012-488d-b4e1-aa0f83f294bb
caps.latest.revision: 25
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
ms.openlocfilehash: 2e0b082be6aac7314d8251f89b42ed09e44e2f3d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cusertool-class"></a>Класс CUserTool
Пользовательский инструмент — это пункт меню, который запускает внешнее приложение. **Средства** вкладке **Настройка** диалоговое окно ( [CMFCToolBarsCustomizeDialog класса](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)) позволяет пользователю добавить пользовательские инструменты и укажите имя, команду, аргументы и начальный каталог для каждого пользовательского средства.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CUserTool : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUserTool::CopyIconToClipboard](#copyicontoclipboard)||  
|[CUserTool::DrawToolIcon](#drawtoolicon)|Значок средства пользователь рисует в заданном прямоугольнике.|  
|[CUserTool::GetCommand](#getcommand)|Возвращает строку, содержащую текст команды, связанные с инструментом пользователя.|  
|[CUserTool::GetCommandId](#getcommandid)|Возвращает идентификатор команды меню средства user.|  
|[CUserTool::Invoke](#invoke)|Выполняет команду, связанную со средством пользователя.|  
|[CUserTool::Serialize](#serialize)|Считывает этот объект из архива или записывает в него. (Переопределяет [CObject::Serialize](../../mfc/reference/cobject-class.md#serialize).)|  
|[CUserTool::SetCommand](#setcommand)|Задает команду, связанную со средством пользователя.|  
|[CUserTool::SetToolIcon](#settoolicon)|Загружает значок программы пользователя из приложения, связанного с помощью средства.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUserTool::LoadDefaultIcon](#loaddefaulticon)|Загружает значок по умолчанию для пользовательский инструмент.|  
  
### <a name="data-members"></a>Элементы данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CUserTool::m_strArguments](#m_strarguments)|Аргументы командной строки для средства пользователя.|  
|[CUserTool::m_strInitialDirectory](#m_strinitialdirectory)|Исходный каталог программы пользователя.|  
|[CUserTool::m_strLabel](#m_strlabel)|Имя средства, отображаемый в меню программы.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о включении средства пользователя в приложении см. в разделе [CUserToolsManager класса](../../mfc/reference/cusertoolsmanager-class.md).  
  
## <a name="example"></a>Пример  
 В следующем примере демонстрируется создание средства из `CUserToolsManager` объекта `m_strLabel` переменной-члена, а также установите приложение, которое запускает средство пользовательского. Этот фрагмент кода является частью [Visual Studio демонстрационного](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo&#35;](../../mfc/codesnippet/cpp/cusertool-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CUserTool](../../mfc/reference/cusertool-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxusertool.h  
  
##  <a name="copyicontoclipboard"></a>CUserTool::CopyIconToClipboard  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
BOOL CopyIconToClipboard();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="drawtoolicon"></a>CUserTool::DrawToolIcon  
 Значок средства пользователь рисует в центре заданного прямоугольника.  
  
```  
void DrawToolIcon(
    CDC* pDC,  
    const CRect& rectImage);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `pDC`  
 Указатель на контекст устройства.  
  
 [in] `rectImage`  
 Задает координаты области для отображения значка.  
  
##  <a name="getcommand"></a>CUserTool::GetCommand  
 Возвращает строку, содержащую текст команды, связанные с инструментом пользователя.  
  
```  
const CString& GetCommand() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `CString` объект, содержащий текст команды, связанные с инструментом пользователя.  
  
##  <a name="getcommandid"></a>CUserTool::GetCommandId  
 Возвращает идентификатор команды инструмента пользователя.  
  
```  
UINT GetCommandId() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор команды этого средства пользователя.  
  
##  <a name="invoke"></a>CUserTool::Invoke  
 Выполняет команду, связанную со средством пользователя.  
  
```  
virtual BOOL Invoke();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если данная команда была выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Вызовы [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) для выполнения команды, связанные с инструментом пользователя. Операция завершается ошибкой, если команда является пустым или [ShellExecute](http://msdn.microsoft.com/library/windows/desktop/bb762153) завершается ошибкой.  
  
##  <a name="loaddefaulticon"></a>CUserTool::LoadDefaultIcon  
 Загружает значок по умолчанию для пользовательский инструмент.  
  
```  
virtual HICON LoadDefaultIcon();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для загрузки значок ( `HICON`), или `NULL` , если не удается загрузить значок по умолчанию.  
  
### <a name="remarks"></a>Примечания  
 Платформа вызывает этот метод, когда не удается загрузить значок для определяемых пользователем средства из исполняемого файла программы.  
  
 Переопределите этот метод, чтобы предоставить собственный значок средства по умолчанию.  
  
##  <a name="m_strarguments"></a>CUserTool::m_strArguments  
 Аргументы командной строки для средства пользователя.  
  
```  
CString m_strArguments;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта строка передается средству при вызове [CUserTool::Invoke](#invoke) или когда пользователь щелкает команду, связанную с помощью этого средства.  
  
##  <a name="m_strinitialdirectory"></a>CUserTool::m_strInitialDirectory  
 Задает начальный каталог для пользователя средства.  
  
```  
CString m_strInitialDirectory;  
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная определяет начальный каталог, эта программа выполняется в при вызове [CUserTool::Invoke](#invoke) или когда пользователь щелкает команду, связанную с помощью этого средства.  
  
##  <a name="m_strlabel"></a>CUserTool::m_strLabel  
 Метка, которая отображается в меню программы.  
  
```  
CString m_strLabel;  
```  
  
##  <a name="serialize"></a>CUserTool::Serialize  
 [!INCLUDE[cpp_fp_under_construction](../../mfc/reference/includes/cpp_fp_under_construction_md.md)]  
  
```  
virtual void Serialize(CArchive& ar);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `ar`  
  
### <a name="remarks"></a>Примечания  
  
##  <a name="setcommand"></a>CUserTool::SetCommand  
 Задает приложение, которое запускает средство пользователя.  
  
```  
void SetCommand(LPCTSTR lpszCmd);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszCmd`  
 Указывает новое приложение, необходимо сопоставить со средством пользователя.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для установки нового приложения, которое запускается средство пользователя. Этот метод удаляет старые значок и загружает новый значок из данного приложения. Если его не удается загрузить значок из приложения, он загружает значок по умолчанию для пользователя средства путем вызова [CUserTool::LoadDefaultIcon](#loaddefaulticon).  
  
##  <a name="settoolicon"></a>CUserTool::SetToolIcon  
 Загружает значок программы пользователя из приложения, который используется средством.  
  
```  
virtual HICON SetToolIcon();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор загрузить значок.  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется для загрузки значка, отображаемого в элементе меню. Этот метод осуществляет поиск значок в исполняемом файле, который используется средством. Если он имеет значок по умолчанию, предоставляемые значок [CUserTool::LoadDefaultIcon](#loaddefaulticon) вместо него используется.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx Class](../../mfc/reference/cwinappex-class.md)   
 [Класс CUserToolsManager](../../mfc/reference/cusertoolsmanager-class.md)

