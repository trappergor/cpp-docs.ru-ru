---
title: "CHotKeyCtrl-класс | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHotKeyCtrl
dev_langs:
- C++
helpviewer_keywords:
- hot key controls
- CHotKeyCtrl class
- Windows common controls [C++], CHotKeyCtrl
ms.assetid: 896f9766-0718-4f58-aab2-20325e118ca6
caps.latest.revision: 23
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: cbcc720d2b934cde9f8beb9bb95499d9cc569413
ms.lasthandoff: 02/24/2017

---
# <a name="chotkeyctrl-class"></a>CHotKeyCtrl-класс
Предоставляет функциональные возможности стандартного элемента управления "горячая клавиша" Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CHotKeyCtrl : public CWnd  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHotKeyCtrl::CHotKeyCtrl](#chotkeyctrl)|Создает объект `CHotKeyCtrl`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHotKeyCtrl::Create](#create)|Создает элемент управления горячей ключа и присоединяется к `CHotKeyCtrl` объекта.|  
|[CHotKeyCtrl::CreateEx](#createex)|Создает элемент управления горячей ключа с указанным расширенные стили Windows и присоединяется к `CHotKeyCtrl` объекта.|  
|[CHotKeyCtrl::GetHotKey](#gethotkey)|Получает виртуальный ключа код и модификатор флаги сочетания клавиш из горячей ключа элемента управления.|  
|[CHotKeyCtrl::GetHotKeyName](#gethotkeyname)|Возвращает имя ключа локального кодировка, назначенные сочетания клавиш.|  
|[CHotKeyCtrl::GetKeyName](#getkeyname)|Возвращает имя ключа локального кодировка, назначенные указанным виртуальный код клавиши.|  
|[CHotKeyCtrl::SetHotKey](#sethotkey)|Задает горячей сочетание клавиш для горячей ключа элемента управления.|  
|[CHotKeyCtrl::SetRules](#setrules)|Определяет недопустимые комбинации и сочетания модификатор по умолчанию для горячей ключа элемента управления.|  
  
## <a name="remarks"></a>Примечания  
 «Горячей ключа управления» представляет собой окно, пользователь может создать сочетания клавиш. «Сочетания клавиш» является сочетание клавиш, которое пользователь может нажать для быстрого выполнения действия. (Например, пользователя можно создать сочетание клавиш, которое активирует данного окна и переводит ее в начало Z-порядка). Горячий ключа выводит выборы пользователя и гарантирует, что пользователь выберет допустимое сочетание клавиш.  
  
 Этот элемент управления (и, следовательно, `CHotKeyCtrl` класса) доступны только для программы, запущенные в Windows 95/98 и Windows NT версии 3.51 и более поздних версий.  
  
 Если пользователь выбрал сочетание клавиш, приложение может получить заданное сочетание клавиш в элементе управления и использовать **WM_SETHOTKEY** сообщений, чтобы настроить сочетания клавиш в системе. Каждый раз, когда пользователь нажимает сочетание клавиш в дальнейшем из любой части системы, окно указано в **WM_SETHOTKEY** получает сообщение `WM_SYSCOMMAND` указание сообщение **SC_HOTKEY**. Это сообщение активирует окно, которое получает его. Сочетания клавиш остается действительным, пока приложение, которое называется **WM_SETHOTKEY** завершает работу.  
  
 Этот механизм отличается от горячего поддержка ключа, зависит от **WM_HOTKEY** сообщений и Windows [RegisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646309) и [UnregisterHotKey](http://msdn.microsoft.com/library/windows/desktop/ms646327) функции.  
  
 Дополнительные сведения об использовании `CHotKeyCtrl`, в разделе [управления](../../mfc/controls-mfc.md) и [CHotKeyCtrl с помощью](../../mfc/using-chotkeyctrl.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CHotKeyCtrl`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxcmn.h  
  
##  <a name="a-namechotkeyctrla--chotkeyctrlchotkeyctrl"></a><a name="chotkeyctrl"></a>CHotKeyCtrl::CHotKeyCtrl  
 Создает объект `CHotKeyCtrl`.  
  
```  
CHotKeyCtrl();
```  
  
##  <a name="a-namecreatea--chotkeyctrlcreate"></a><a name="create"></a>CHotKeyCtrl::Create  
 Создает элемент управления горячей ключа и присоединяется к `CHotKeyCtrl` объекта.  
  
```  
virtual BOOL Create(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwStyle`  
 Задает стиль горячей ключа элемента управления. Примените любое сочетание стилей элемента управления. В разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] для получения дополнительной информации.  
  
 `rect`  
 Задает размер и положение горячей ключа элемента управления. Это может быть либо [CRect](../../atl-mfc-shared/reference/crect-class.md) объекта или [структура RECT](../../mfc/reference/rect-structure1.md).  
  
 `pParentWnd`  
 Задает сочетания клавиш управления родительского окна, обычно [CDialog](../../mfc/reference/cdialog-class.md). Оно не должно быть **NULL**.  
  
 `nID`  
 Указывает идентификатор горячей ключа элемента управления.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если инициализация выполнена успешно; в противном случае — 0.  
  
### <a name="remarks"></a>Примечания  
 Создании `CHotKeyCtrl` объекта в два этапа. Во-первых, вызовите конструктор, а затем вызвать **создать**, который создает горячей ключа элемента управления и присоединяет его к `CHotKeyCtrl` объекта.  
  
 Если вы хотите использовать с элементом управления windows расширенные стили, вызвать [CreateEx](#createex) вместо **создать**.  
  
##  <a name="a-namecreateexa--chotkeyctrlcreateex"></a><a name="createex"></a>CHotKeyCtrl::CreateEx  
 Эта функция вызывается для создания элемента управления (дочернего окна) и связать его с `CHotKeyCtrl` объекта.  
  
```  
virtual BOOL CreateEx(
    DWORD dwExStyle,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    UINT nID);
```  
  
### <a name="parameters"></a>Параметры  
 `dwExStyle`  
 Указывает расширенный стиль создаваемого элемента управления. Список расширенных стилей Windows см. в разделе `dwExStyle` параметр [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `dwStyle`  
 Задает стиль горячей ключа элемента управления. Примените любое сочетание стилей элемента управления. Дополнительные сведения см. в разделе [общие стили элемента управления](http://msdn.microsoft.com/library/windows/desktop/bb775498) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `rect`  
 Ссылку на [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) структуры, описывающее размер и положение окна, чтобы создать, в клиентских координат `pParentWnd`.  
  
 `pParentWnd`  
 Указатель на окно, который является родительским для элемента управления.  
  
 `nID`  
 Идентификатор элемента управления дочернего окна.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имеет ненулевое значение в случае успешного выполнения, иначе — 0.  
  
### <a name="remarks"></a>Примечания  
 Используйте `CreateEx` вместо [создать](#create) для применения расширенных стилей Windows, заданные к ней префикс расширенный стиль Windows **WS_EX_**.  
  
##  <a name="a-namegethotkeya--chotkeyctrlgethotkey"></a><a name="gethotkey"></a>CHotKeyCtrl::GetHotKey  
 Получает виртуальный ключа код и модификатор флаги сочетания клавиш из горячей ключа элемента управления.  
  
```  
DWORD GetHotKey() const;  
  
void GetHotKey(
    WORD& wVirtualKeyCode,  
    WORD& wModifiers) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [выходной] `wVirtualKeyCode`  
 Виртуальный код клавиши сочетания клавиш. Список стандартных кодов виртуального ключа см. в разделе Winuser.h.  
  
 [выходной] `wModifiers`  
 Побитовое сочетание (или) флагов, указывающих клавиши-модификаторы клавиш.  
  
 Флаги модификаторов выглядят следующим образом:  
  
|Flag|Соответствующий ключ|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT - клавиша|  
|`HOTKEYF_CONTROL`|Нажмите клавишу CTRL|  
|`HOTKEYF_EXT`|Расширенные ключ|  
|`HOTKEYF_SHIFT`|Клавиша SHIFT|  
  
### <a name="return-value"></a>Возвращаемое значение  
 В первом перегруженный метод, `DWORD` , содержащий виртуальный ключа кода и флаги модификаторов. Младший байт младшее слово содержит виртуальный код клавиши, старший байт младшее слово содержит флаги модификаторов и старшее слово равно нулю.  
  
### <a name="remarks"></a>Примечания  
 Виртуальный код клавиши и клавиши-модификаторы вместе определяют сочетания клавиш.  
  
##  <a name="a-namegethotkeynamea--chotkeyctrlgethotkeyname"></a><a name="gethotkeyname"></a>CHotKeyCtrl::GetHotKeyName  
 Вызовите эту функцию-член для получения локализованное имя сочетания клавиш.  
  
```  
CString GetHotKeyName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Локализованное имя выбранного сочетания клавиш. Если нет выбранных горячей ключа `GetHotKeyName` возвращает пустую строку.  
  
### <a name="remarks"></a>Примечания  
 Имя, которое возвращает эта функция-член поступают из драйвер клавиатуры. Можно установить драйвер нелокализованное клавиатуры в локализованных версиях Windows и наоборот.  
  
##  <a name="a-namegetkeynamea--chotkeyctrlgetkeyname"></a><a name="getkeyname"></a>CHotKeyCtrl::GetKeyName  
 Вызовите эту функцию-член для получения локализованных имя ключа, назначенные указанным виртуальный код клавиши.  
  
```  
static CString GetKeyName(
    UINT vk,  
    BOOL fExtended);
```  
  
### <a name="parameters"></a>Параметры  
 `vk`  
 Виртуальный код клавиши.  
  
 *fExtended*  
 Если виртуальный код клавиши является ключом расширенного **TRUE**; в противном случае **FALSE**.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Локализованное имя ключа, заданного параметром `vk` параметр. Если ключ не имеет сопоставленного имени, `GetKeyName` возвращает пустую строку.  
  
### <a name="remarks"></a>Примечания  
 Имя ключа, которое возвращает эта функция поступает из драйвер клавиатуры, чтобы установить драйвер нелокализованное клавиатуры в локализованных версиях Windows и наоборот.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCControlLadenDialog&#69;](../../mfc/codesnippet/cpp/chotkeyctrl-class_1.cpp)]  
  
##  <a name="a-namesethotkeya--chotkeyctrlsethotkey"></a><a name="sethotkey"></a>CHotKeyCtrl::SetHotKey  
 Задает сочетание клавиш для горячей ключа элемента управления.  
  
```  
void SetHotKey(
    WORD wVirtualKeyCode,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `wVirtualKeyCode`  
 Виртуальный код клавиши сочетания клавиш. Список стандартных кодов виртуального ключа см. в разделе Winuser.h.  
  
 [in] `wModifiers`  
 Побитовое сочетание (или) флагов, указывающих клавиши-модификаторы клавиш.  
  
 Флаги модификаторов выглядят следующим образом:  
  
|Flag|Соответствующий ключ|  
|----------|-----------------------|  
|`HOTKEYF_ALT`|ALT - клавиша|  
|`HOTKEYF_CONTROL`|Нажмите клавишу CTRL|  
|`HOTKEYF_EXT`|Расширенные ключ|  
|`HOTKEYF_SHIFT`|Клавиша SHIFT|  
  
### <a name="remarks"></a>Примечания  
 Виртуальный код клавиши и клавиши-модификаторы вместе определяют сочетания клавиш.  
  
##  <a name="a-namesetrulesa--chotkeyctrlsetrules"></a><a name="setrules"></a>CHotKeyCtrl::SetRules  
 Эта функция вызывается для определения недопустимые комбинации и сочетания модификатор по умолчанию для горячей ключа элемента управления.  
  
```  
void SetRules(
    WORD wInvalidComb,  
    WORD wModifiers);
```  
  
### <a name="parameters"></a>Параметры  
 `wInvalidComb`  
 Массив флагов, задающий недопустимые сочетания клавиш. Это может быть сочетание следующих значений:  
  
- `HKCOMB_A`ALT  
  
- `HKCOMB_C`CTRL  
  
- `HKCOMB_CA`CTRL + ALT  
  
- `HKCOMB_NONE`Неизмененный ключей  
  
- `HKCOMB_S`SHIFT  
  
- `HKCOMB_SA`SHIFT + ALT  
  
- `HKCOMB_SC`SHIFT + CTRL  
  
- `HKCOMB_SCA`SHIFT + CTRL + ALT  
  
 `wModifiers`  
 Массив флагов, задающий сочетание клавиш для использования, когда пользователь вводит недопустимое сочетание. Дополнительные сведения о флагах модификатор см [GetHotKey](#gethotkey).  
  
### <a name="remarks"></a>Примечания  
 Если пользователь вводит недопустимое сочетание клавиш, как определяется флагов, заданных в `wInvalidComb`, система использует оператор OR для объединения ключей, введенные пользователем с помощью флагов, заданных в `wModifiers`. Получившееся в результате сочетание клавиш преобразуется в строку и затем отображаются в элементе управления горячей ключа.  
  
## <a name="see-also"></a>См. также  
 [CWnd-класс](../../mfc/reference/cwnd-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




