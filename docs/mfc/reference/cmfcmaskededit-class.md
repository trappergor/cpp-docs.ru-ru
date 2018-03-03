---
title: "Класс CMFCMaskedEdit | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit
- AFXMASKEDEDIT/CMFCMaskedEdit::DisableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableGetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableMask
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSelectByGroup
- AFXMASKEDEDIT/CMFCMaskedEdit::EnableSetMaskedCharsOnly
- AFXMASKEDEDIT/CMFCMaskedEdit::GetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::SetValidChars
- AFXMASKEDEDIT/CMFCMaskedEdit::SetWindowText
- AFXMASKEDEDIT/CMFCMaskedEdit::IsMaskedChar
dev_langs:
- C++
helpviewer_keywords:
- CMFCMaskedEdit [MFC], DisableMask
- CMFCMaskedEdit [MFC], EnableGetMaskedCharsOnly
- CMFCMaskedEdit [MFC], EnableMask
- CMFCMaskedEdit [MFC], EnableSelectByGroup
- CMFCMaskedEdit [MFC], EnableSetMaskedCharsOnly
- CMFCMaskedEdit [MFC], GetWindowText
- CMFCMaskedEdit [MFC], SetValidChars
- CMFCMaskedEdit [MFC], SetWindowText
- CMFCMaskedEdit [MFC], IsMaskedChar
ms.assetid: 13b1a645-2d5d-4c37-8599-16d5003f23a5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b0ada987b3226d901c3bf01236c2a593c2e36f51
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cmfcmaskededit-class"></a>Класс CMFCMaskedEdit
`CMFCMaskedEdit` Класс поддерживает элемент управления masked edit, который проверяет введенные пользователем данные, соответствие маске и отображает установленные результаты в соответствии с шаблоном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Конструктор по умолчанию.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|Отключение проверки введенных пользователем данных.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Указывает, является ли `GetWindowText` метод извлекает только маскированные символы.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|Инициализирует скрытого поля ввода.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Указывает, выбираются ли элемент управления masked edit определенным группам вводимых пользователем данных или всех вводимых пользователем данных.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Определяет текст проверяется только скрытые символы, или для всей маски.|  
|`CMFCMaskedEdit::GetThisClass`|Используется платформой для получения указателя на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Извлекает проверить текст в элемент управления masked edit.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Задает строку, допустимых символов, которые пользователь может ввести.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Выводит запрос в элемент управления masked edit.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Вызывается платформой для проверки указанный символ для соответствующего символа маски.|  
  
## <a name="remarks"></a>Примечания  
 Выполните следующие действия для использования `CMFCMaskedEdit` элемента управления в приложении:  
  
 1. Внедрение `CMFCMaskedEdit` объект в класс окна.  
  
 2. Вызовите [CMFCMaskedEdit::EnableMask](#enablemask) метод, чтобы задать маску.  
  
 3. Вызовите [CMFCMaskedEdit::SetValidChars](#setvalidchars) метод, чтобы указать список допустимых символов.  
  
 4. Вызовите [CMFCMaskedEdit::SetWindowText](#setwindowtext) метод, чтобы задать текст по умолчанию для управления masked edit.  
  
 5. Вызовите [CMFCMaskedEdit::GetWindowText](#getwindowtext) метод для извлечения текста, проверяется.  
  
 Если не нужно вызывать один или несколько методов для инициализации маски, допустимые символы и текст по умолчанию, элемент управления masked edit ведет себя так же, как ведет себя стандартного элемента управления правки.  
  
## <a name="example"></a>Пример  
 Ниже приведен пример, как настроить маску (например, номер телефона) с помощью `EnableMask` метод для создания маски для скрытого элемента управления edit, `SetValidChars` метод для указания строки допустимых символов, которые пользователь может ввести и `SetWindowText` метод, чтобы отобразить строку в скрытый элемент управления. Данный пример является частью [образец новые элементы управления](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#11](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#12](../../mfc/reference/codesnippet/cpp/cmfcmaskededit-class_2.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCMaskedEdit](../../mfc/reference/cmfcmaskededit-class.md)  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxmaskededit.h  
  
##  <a name="disablemask"></a>CMFCMaskedEdit::DisableMask  
 Отключение проверки введенных пользователем данных.  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>Примечания  
 Если отключена проверка введенных пользователем данных, элемент управления masked edit ведет себя как стандартный элемент управления.  
  
##  <a name="enablegetmaskedcharsonly"></a>CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 Указывает, является ли `GetWindowText` метод извлекает только маскированные символы.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы указать, что [CMFCMaskedEdit::GetWindowText](#getwindowtext) метод получить только скрытые символы; `FALSE` для указания, что метод получить весь текст. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод, чтобы включить получение маскированные символы. Создайте элемент управления masked edit, соответствующий номер телефона, например (425) 555-0187. При вызове метода `GetWindowText` , она возвращает «4255550187». Если отключить получение маскированные символы `GetWindowText` метод возвращает текст, отображаемый в элементе управления редактированием, например «(425) 555-0187».  
  
##  <a name="enablemask"></a>CMFCMaskedEdit::EnableMask  
 Инициализирует скрытого поля ввода.  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszMask`  
 Маска строка, указывающая тип символа, который может встречаться в каждой позиции вводимых пользователем данных. Длина `lpszInputTemplate` и `lpszMask` строки параметров должны быть одинаковыми. В разделе «Примечания» для получения дополнительных сведений о символах маски.  
  
 [in] `lpszInputTemplate`  
 Строка шаблона маски, указывает, что литерал символов, которое может присутствовать на Каждая позиция в вводимых пользователем данных. Используйте символ подчеркивания (_) в качестве заполнителя знак. Длина `lpszInputTemplate` и `lpszMask` строки параметров должны быть одинаковыми.  
  
 [in] `chMaskInputTemplate`  
 Символ по умолчанию, который замещает платформу для каждый недопустимый символ в вводимых пользователем данных. Значение этого параметра по умолчанию является символ подчеркивания (_).  
  
 [in] `lpszValid`  
 Строка, содержащая набор допустимых символов. `NULL`Указывает, что все символы являются допустимыми. По умолчанию этот параметр имеет значение `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для создания маски для элемент управления masked edit. Производный класс `CMFCMaskedEdit` класса и переопределить [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) метод, чтобы использовать собственный код для обработки пользовательских маски.  
  
 В приведенной ниже таблице представлены символы маски по умолчанию:  
  
|Символ маски|Определение|  
|--------------------|----------------|  
|Н|Цифра.|  
|d|Цифра или пробел.|  
|+|Плюс («+»), минус ("-"), или пробел.|  
|В|Символ является буквой алфавита.|  
|c|Буквенный символ или пробел.|  
|А|Буквенно-цифровой символ.|  
|пример|Буквенно-цифровой символ или пробел.|  
|*|Печатный символ.|  
  
##  <a name="enableselectbygroup"></a>CMFCMaskedEdit::EnableSelectByGroup  
 Указывает, допускает ли элемент управления masked edit пользователю входных данных для выбора определенных групп или все входные данные.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`Чтобы выбрать только группы; `FALSE` выделите весь текст. Значение по умолчанию — `TRUE`.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для указания, является ли элемент управления masked edit позволяет пользователю выбирать по группам или по всему тексту.  
  
 По умолчанию включен выбор по группе. В этом случае пользователь может выбрать только непрерывные группы допустимые символы.  
  
 Например следующий элемент управления masked edit может использовать для проверки телефонный номер:  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 Если выбор по группе включен, пользователь может извлечь только «425», «555» или «0187» строки групп. Если выбрать группу отключено пользователь может извлечь весь текст и номер телефона: «(425) 555-0187».  
  
##  <a name="enablesetmaskedcharsonly"></a>CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 Указывает, проверяется ли текст для только маскированные символы, или для всей маски.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `bEnable`  
 `TRUE`для проверки пользователя введенных только скрытые символы; `FALSE` для проверки соответствия всей маски. Значение по умолчанию — `TRUE`.  
  
##  <a name="getwindowtext"></a>CMFCMaskedEdit::GetWindowText  
 Извлекает проверить текст в элемент управления masked edit.  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `lpszStringBuf`  
 Указатель на буфер, получающий из элемента управления редактирования текста.  
  
 [in] `nMaxCount`  
 Максимальное количество символов для получения.  
  
 [выходной] `rstrString`  
 Ссылка на строковый объект, который получает текст из поля ввода.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первая перегрузка метода возвращает количество байт строки, в который копируется в `lpszStringBuf` буфер параметра; 0, если элемент управления masked edit не содержит текста.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует текст в элемент управления masked edit для `lpszStringBuf` буфера или `rstrString` строки.  
  
 Этот метод переопределяет [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).  
  
##  <a name="ismaskedchar"></a>CMFCMaskedEdit::IsMaskedChar  
 Вызывается платформой для проверки указанный символ для соответствующего символа маски.  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in] `chChar`  
 Знак, который необходимо проверить.  
  
 [in] `chMaskChar`  
 Соответствующий символ из строки маски.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если `chChar` параметр имеет тип символа, допускаемой `chMaskChar` параметр; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для проверки ввода символов вручную. Дополнительные сведения о символах маска см. в разделе [CMFCMaskedEdit::EnableMask](#enablemask) метод.  
  
##  <a name="setvalidchars"></a>CMFCMaskedEdit::SetValidChars  
 Задает строку, допустимых символов, которые пользователь может ввести.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszValid`  
 Строка, содержащая набор допустимых входных символов. `NULL`означает, что все символы являются допустимыми. По умолчанию этот параметр имеет значение `NULL`.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для определения списка допустимых символов. Если входной символ не является в этом списке, он не будет принимать в элемент управления masked edit.  
  
 В следующем примере кода принимает только шестнадцатеричные цифры.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>CMFCMaskedEdit::SetWindowText  
 Выводит запрос в элемент управления masked edit.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `lpszString`  
 Указывает символом null строку, которая будет использоваться в качестве запроса.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает текст элемента управления.  
  
 Этот метод переопределяет [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)
