---
title: Класс CMFCMaskedEdit | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a0bb29fdaff72370ec197fc9b3f651b5ff574c32
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45717435"
---
# <a name="cmfcmaskededit-class"></a>Класс CMFCMaskedEdit
`CMFCMaskedEdit` Класс поддерживает элемент управления masked edit, который проверяет введенные пользователем данные соответствие маске и отображает установленные результаты в соответствии с шаблоном.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMFCMaskedEdit : public CEdit  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|`CMFCMaskedEdit::CMFCMaskedEdit`|Конструктор по умолчанию.|  
|`CMFCMaskedEdit::~CMFCMaskedEdit`|Деструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCMaskedEdit::DisableMask](#disablemask)|Отключение проверки ввода пользователя.|  
|[CMFCMaskedEdit::EnableGetMaskedCharsOnly](#enablegetmaskedcharsonly)|Указывает, является ли `GetWindowText` метод извлекает только маскированные символы.|  
|[CMFCMaskedEdit::EnableMask](#enablemask)|Инициализирует скрытого поля ввода.|  
|[CMFCMaskedEdit::EnableSelectByGroup](#enableselectbygroup)|Указывает, выбирает ли элемент управления masked edit определенным группам вводимых пользователем данных или весь пользовательский ввод.|  
|[CMFCMaskedEdit::EnableSetMaskedCharsOnly](#enablesetmaskedcharsonly)|Определяет текст проверяется на соответствие только маскируются символами, или для всей маски.|  
|`CMFCMaskedEdit::GetThisClass`|Используется инфраструктурой, чтобы получить указатель на [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) объект, связанный с этим типом класса.|  
|[CMFCMaskedEdit::GetWindowText](#getwindowtext)|Извлекает проверить текст из элемент управления masked edit.|  
|[CMFCMaskedEdit::SetValidChars](#setvalidchars)|Задает строку, допустимых символов, которые пользователь может ввести.|  
|[CMFCMaskedEdit::SetWindowText](#setwindowtext)|Отображает запрос в элемент управления masked edit.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMFCMaskedEdit::IsMaskedChar](#ismaskedchar)|Вызывается платформой для проверки указанного знака от соответствующего символа маски.|  
  
## <a name="remarks"></a>Примечания  
 Выполните следующие действия для использования `CMFCMaskedEdit` элемента управления в приложении:  
  
 1. Внедрение `CMFCMaskedEdit` объект в класс окна.  
  
 2. Вызовите [CMFCMaskedEdit::EnableMask](#enablemask) метод, чтобы задать маску.  
  
 3. Вызовите [CMFCMaskedEdit::SetValidChars](#setvalidchars) метод, чтобы задать список допустимых символов.  
  
 4. Вызовите [CMFCMaskedEdit::SetWindowText](#setwindowtext) метод, чтобы задать текст по умолчанию для элемента управления masked edit.  
  
 5. Вызовите [CMFCMaskedEdit::GetWindowText](#getwindowtext) метод для получения проверенных текста.  
  
 Если вы не вызываете один или несколько методов для инициализации маску, допустимые символы и текст по умолчанию, элемент управления masked edit ведет себя так же, как ведет себя стандартного элемента управления правки.  
  
## <a name="example"></a>Пример  
 Приведенный ниже показано, как настроить маску (например, номер телефона) с помощью `EnableMask` метод для создания маски для скрытого элемента управления, edit `SetValidChars` метод, чтобы задать строку допустимые символы, которые пользователь может ввести и `SetWindowText` метод для отображения в строке в скрытого элемента управления edit. Этот пример является частью [пример новых элементов управления](../../visual-cpp-samples.md).  
  
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
  
##  <a name="disablemask"></a>  CMFCMaskedEdit::DisableMask  
 Отключение проверки ввода пользователя.  
  
```  
void DisableMask();
```  
  
### <a name="remarks"></a>Примечания  
 Если отключена проверка введенных пользователем данных, элемент управления masked edit ведет себя так, как и стандартный элемент управления.  
  
##  <a name="enablegetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableGetMaskedCharsOnly  
 Указывает, является ли `GetWindowText` метод извлекает только маскированные символы.  
  
```  
void EnableGetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*bEnable*<br/>
[in] Значение TRUE, чтобы указать, что [CMFCMaskedEdit::GetWindowText](#getwindowtext) метод извлечения только маскируются символов; Значение FALSE, чтобы указать, что метод получения по всему тексту. Значение по умолчанию — TRUE.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет включить получение маскированные символы. Создайте элемент управления masked edit, соответствующий номер телефона, например (425) 555-0187. При вызове метода `GetWindowText` метод, он возвращает «4255550187». Если отключить получение маскированные символы `GetWindowText` метод возвращает текст, отображаемый в элементе управления, например «(425) 555-0187».  
  
##  <a name="enablemask"></a>  CMFCMaskedEdit::EnableMask  
 Инициализирует скрытого поля ввода.  
  
```  
void EnableMask(
    LPCTSTR lpszMask,  
    LPCTSTR lpszInputTemplate,  
    TCHAR chMaskInputTemplate=_T('_'),  
    LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Параметры  
*lpszMask*<br/>
[in] Строка маска, указывающая тип символа, который может появляться в каждой позиции в вводимых пользователем данных. Длина *lpszInputTemplate* и *lpszMask* строки параметров должны быть одинаковыми. Дополнительные сведения о символах маски в разделе "Примечания".  
  
*lpszInputTemplate*<br/>
[in] Строка шаблона маски, в которой указывается литерала символов, который может присутствовать в каждой позиции в вводимых пользователем данных. Используйте символ подчеркивания («_») в качестве заполнителя символов. Длина *lpszInputTemplate* и *lpszMask* строки параметров должны быть одинаковыми.  
  
*chMaskInputTemplate*<br/>
[in] Символ по умолчанию, который замещает платформы для каждый недопустимый символ в вводимых пользователем данных. Значение по умолчанию этого параметра — символ подчеркивания («_»).  
  
*lpszValid*<br/>
[in] Строка, содержащая набор допустимых символов. Значение NULL указывает, что все символы являются допустимыми. Значение по умолчанию этого параметра равно NULL.  
  
### <a name="remarks"></a>Примечания  
 Используйте этот метод для создания маски для элемент управления masked edit. Наследуйте класс от `CMFCMaskedEdit` класса и переопределить [CMFCMaskedEdit::IsMaskedChar](#ismaskedchar) метод, чтобы использовать собственный код для обработки пользовательских маски.  
  
 В следующей таблице перечислены символы маски по умолчанию:  
  
|Символ маски|Определение|  
|--------------------|----------------|  
|Н|Цифра.|  
|d|Цифра или пробел.|  
|+|Плюс («+»), минус ("-"), или пробел.|  
|В|Символ является буквой алфавита.|  
|c|Алфавитный символ или пробел.|  
|А|Буквенно-цифровой символ.|  
|пример|Буквенно-цифровой символ или пробел.|  
|*|Печатный символ.|  
  
##  <a name="enableselectbygroup"></a>  CMFCMaskedEdit::EnableSelectByGroup  
 Указывает, допускает ли элемент управления masked edit пользователю входные данные для выбора определенных групп или все входные данные.  
  
```  
void EnableSelectByGroup(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*bEnable*<br/>
[in] Значение TRUE, чтобы выбрать только группы; Значение FALSE, чтобы выбрать весь текст. Значение по умолчанию — TRUE.  
  
### <a name="remarks"></a>Примечания  
 Эта функция используется для указания того, допускает ли элемент управления masked edit пользователю выбирать по группе или по всему тексту.  
  
 По умолчанию включен выбор по группе. В этом случае пользователь может выбрать только непрерывные группы допустимых символов.  
  
 Например можно использовать следующий элемент управления masked edit подтверждения номера телефона:  
  
 `m_wndMaskEdit.EnableMask(`  
  
 `_T(" ddd  ddd dddd"),// Mask string`  
  
 `_T("(___) ___-____"),// Template string`  
  
 `_T(' '));// Default char`  
  
 `m_wndMaskEdit.SetValidChars(NULL); // All characters are valid.`  
  
 `m_wndMaskEdit.SetWindowText(_T("(425) 555-0187")); // Prompt`  
  
 Если выбор по группе включен, пользователь может получить только «425», «555» или «0187» строки группы. Если Выбор группы отключен пользователя можно получить по всему тексту номер телефона: «(425) 555-0187».  
  
##  <a name="enablesetmaskedcharsonly"></a>  CMFCMaskedEdit::EnableSetMaskedCharsOnly  
 Указывает, проверяется ли текст для только маскированные символы, или для всей маски.  
  
```  
void EnableSetMaskedCharsOnly(BOOL bEnable=TRUE);
```  
  
### <a name="parameters"></a>Параметры  
*bEnable*<br/>
[in] Значение TRUE для проверки пользовательского ввода от только маскируются символов; Значение FALSE, чтобы проверить всю маски. Значение по умолчанию — TRUE.  
  
##  <a name="getwindowtext"></a>  CMFCMaskedEdit::GetWindowText  
 Извлекает проверить текст из элемент управления masked edit.  
  
```  
int GetWindowText(
    LPTSTR lpszStringBuf,  
    int nMaxCount) const;  
  
void GetWindowText(CString& rstrString) const;  
```  
  
### <a name="parameters"></a>Параметры  
*lpszStringBuf*<br/>
[out] Указатель на буфер, получающий текст из элемента управления редактирования.  
  
*nMaxCount*<br/>
[in] Максимальное количество символов для получения.  
  
*rstrString*<br/>
[out] Ссылка на строковый объект, который получает текст из элемента управления редактирования.  
  
### <a name="return-value"></a>Возвращаемое значение  
 По первой перегрузке метода возвращает количество байтов строки, в который копируется для *lpszStringBuf* буфером параметров; 0, если элемент управления masked edit не содержит текста.  
  
### <a name="remarks"></a>Примечания  
 Этот метод копирует текст в элемент управления masked edit для *lpszStringBuf* буфера или *rstrString* строка.  
  
 Этот метод переопределяет [CWnd::GetWindowText](../../mfc/reference/cwnd-class.md#getwindowtext).  
  
##  <a name="ismaskedchar"></a>  CMFCMaskedEdit::IsMaskedChar  
 Вызывается платформой для проверки указанного знака от соответствующего символа маски.  
  
```  
virtual BOOL IsMaskedChar(
    TCHAR chChar,  
    TCHAR chMaskChar) const;  
```  
  
### <a name="parameters"></a>Параметры  
*chChar*<br/>
[in] Символ для проверки.  
  
*chMaskChar*<br/>
[in] Соответствующий символ из строки маски.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение TRUE, если *chChar* параметр представляет собой тип знака по *chMaskChar* параметра; в противном случае — значение FALSE.  
  
### <a name="remarks"></a>Примечания  
 Переопределите этот метод для проверки ввода символов самостоятельно. Дополнительные сведения о символы маски, см. в разделе [CMFCMaskedEdit::EnableMask](#enablemask) метод.  
  
##  <a name="setvalidchars"></a>  CMFCMaskedEdit::SetValidChars  
 Задает строку, допустимых символов, которые пользователь может ввести.  
  
```  
void SetValidChars(LPCTSTR lpszValid=NULL);
```  
  
### <a name="parameters"></a>Параметры  
*lpszValid*<br/>
[in] Строка, содержащая набор допустимых входных символов. Значение NULL означает, что все символы являются допустимыми. Значение по умолчанию этого параметра равно NULL.  
  
### <a name="remarks"></a>Примечания  
 Этот метод позволяет определить список допустимых символов. Если входной символ не находится в этом списке, он не будет принимать в элемент управления masked edit.  
  
 В следующем примере кода принимает только шестнадцатеричные числа.  
  
 `//Mask: 0xFFFFm_wndMaskEdit.EnableMask( _T(" AAAA"),                // The mask string. _T("0x____"),               // The literal template string. _T('_'));                   // The default character that replaces the backspace character.// Valid string charactersm_wndMaskEdit.SetValidChars(_T("1234567890ABCDEFabcdef"));m_wndMaskEdit.SetWindowText(_T("0x01AF"));`  
  
##  <a name="setwindowtext"></a>  CMFCMaskedEdit::SetWindowText  
 Отображает запрос в элемент управления masked edit.  
  
```  
void SetWindowText(LPCTSTR lpszString);
```  
  
### <a name="parameters"></a>Параметры  
*lpszString*<br/>
[in] Указатель на заканчивающуюся нулем строку, которая будет использоваться в качестве запроса.  
  
### <a name="remarks"></a>Примечания  
 Этот метод задает текст элемента управления.  
  
 Этот метод переопределяет [CWnd::SetWindowText](../../mfc/reference/cwnd-class.md#setwindowtext).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../../mfc/reference/mfc-classes.md)   
 [Класс CEdit](../../mfc/reference/cedit-class.md)
