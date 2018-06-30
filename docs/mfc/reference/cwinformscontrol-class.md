---
title: Класс CWinFormsControl | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CWinFormsControl
- AFXWINFORMS/CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CWinFormsControl
- AFXWINFORMS/CWinFormsControl::CreateManagedControl
- AFXWINFORMS/CWinFormsControl::GetControl
- AFXWINFORMS/CWinFormsControl::GetControlHandle
dev_langs:
- C++
helpviewer_keywords:
- CWinFormsControl [MFC], CWinFormsControl
- CWinFormsControl [MFC], CreateManagedControl
- CWinFormsControl [MFC], GetControl
- CWinFormsControl [MFC], GetControlHandle
ms.assetid: 6406dd7b-fb89-4a18-ac3a-c010d6b6289a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 00ec945c5f0cdbb0c12f49b90719c31bf841ef2f
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/29/2018
ms.locfileid: "37121641"
---
# <a name="cwinformscontrol-class"></a>Класс CWinFormsControl
Предоставляет базовую функцию для размещения элементов управления Windows Forms.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<class TManagedControl>  
class CWinFormsControl : public CWnd  
```  
  
#### <a name="parameters"></a>Параметры  
 `TManagedControl`  
 Элемент управления .NET Framework Windows Forms для отображения в приложении MFC.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinFormsControl::CWinFormsControl](#cwinformscontrol)|Создает объект оболочки элемента управления MFC Windows Forms.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinFormsControl::CreateManagedControl](#createmanagedcontrol)|Создает элемент управления Windows Forms в контейнере MFC.|  
|[CWinFormsControl::GetControl](#getcontrol)|Извлекает указатель на элемент управления Windows Forms.|  
|[CWinFormsControl::GetControlHandle](#getcontrolhandle)|Получает дескриптор элемента управления Windows Forms.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CWinFormsControl::operator-&gt;](#operator_-_gt)|Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.|  
|[CWinFormsControl::operator TManagedControl ^](#operator_tmanagedcontrol)|Приводит тип как указатель на элемент управления Windows Forms.|  
  
## <a name="remarks"></a>Примечания  
 `CWinFormsControl` Класс предоставляет базовые функциональные возможности для размещения элементов управления Windows Forms.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
 Код MFC не следует кэшировать маркеры окно (обычно хранятся в `m_hWnd`). Требуется, чтобы некоторые свойства элемента управления Windows Forms базового Win32 `Window` быть уничтожается и создается заново с помощью `DestroyWindow` и `CreateWindow`. Реализация обрабатывает MFC Windows Forms `Destroy` и `Create` события элементов управления для обновления `m_hWnd` член.  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в тех проектах, которые динамически связываются с MFC (в котором определен AFXDLL).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwinforms.h  
  
##  <a name="createmanagedcontrol"></a>  CWinFormsControl::CreateManagedControl  
 Создает элемент управления Windows Forms в контейнере MFC.  
  
```  
inline BOOL CreateManagedControl(
    System::Type^ pType,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID)  
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);

 
inline BOOL CreateManagedControl(
    DWORD dwStyle,  
    int nPlaceHolderID,  
    CWnd* pParentWnd);

 
inline BOOL CreateManagedControl(
    typename TManagedControl^ pControl,  
    DWORD dwStyle,  
    const RECT& rect,  
    CWnd* pParentWnd,  
    int nID);
```  
  
### <a name="parameters"></a>Параметры  
 *pType*  
 Тип данных элемента управления должен быть создан. Должно быть [тип](https://msdn.microsoft.com/en-us/library/system.type) тип данных.  
  
 *dwStyle*  
 Стиль окна, чтобы применить к элементу управления. Задать сочетание [стили окна](../../mfc/reference/styles-used-by-mfc.md#window-styles). В настоящее время поддерживаются только следующие стили: WS_TABSTOP, WS_VISIBLE, WS_DISABLED и WS_GROUP.  
  
 *Rect*  
 Объект [структура RECT](../../mfc/reference/rect-structure1.md) , определяющий координаты левого верхнего и нижнего правого угла элемента управления (сначала перегрузка только).  
  
 *nPlaceHolderID*  
 Дескриптор элемента управления владельца статических месте помещаются в редакторе ресурсов. Только что созданный элемент управления Windows Forms заменяет статический элемент управления, при условии, что его позиции z порядка и стили (второй перегрузка только).  
  
 *pParentWnd*  
 Указатель на родительское окно.  
  
 *nID*  
 Идентификатор ресурса для назначения только что созданный элемент управления.  
  
 *pControl*  
 Экземпляр элемента управления Windows Forms, должны быть связаны с [CWinFormsControl](../../mfc/reference/cwinformscontrol-class.md) объекта (только для четвертого перегрузку).  
  
### <a name="return-value"></a>Возвращаемое значение  
 В случае успешного выполнения возвращает ненулевое значение. В случае неудачи возвращает ноль.  
  
### <a name="remarks"></a>Примечания  
 Этот метод создает элемент управления .NET Framework Windows Forms в контейнере MFC.  
  
 Первый перегруженный метод принимает тип данных .NET Framework *pType* , чтобы MFC можно создать экземпляр объекта этого типа. *pType* должно быть [тип](https://msdn.microsoft.com/en-us/library/system.type) тип данных.  
  
 Вторая перегрузка метода создает элемент управления Windows Forms на основе `TManagedControl` параметр шаблона `CWinFormsControl` класса. Размер и положение элемента управления основан на `RECT` структуры передается в метод. Только *dwStyle* имеет значение для стилей.  
  
 Третья перегрузка метода создает элемент управления Windows Forms, заменяет статический элемент управления, его уничтожение и при условии, что его позиции z порядка и стили. Статический элемент управления используется только как заполнитель для элемента управления Windows Forms. При создании элемента управления, эта перегрузка объединяет стили из *dwStyle* со стилями ресурса статического элемента управления.  
  
 Четвертый перегрузка метода позволяет передавать в элементе управления Windows Forms готовый *pControl* , будет переносить MFC. Он должен быть того же типа, что `TManagedControl` параметр шаблона `CWinFormsControl` класса.  
  
 В разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md) примеры формы Windows Forms с помощью элементов управления.  
  
##  <a name="cwinformscontrol"></a>  CWinFormsControl::CWinFormsControl  
 Создает объект оболочки элемента управления MFC Windows Forms.  
  
```  
CWinFormsControl();
```  
  
### <a name="remarks"></a>Примечания  
 Элемент управления Windows Forms создается при вызове [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrol"></a>  CWinFormsControl::GetControl  
 Извлекает указатель на элемент управления Windows Forms.  
  
```  
inline TManagedControl^ GetControl() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на элемент управления Windows Forms.  
  
### <a name="example"></a>Пример  
  В разделе [CWinFormsControl::CreateManagedControl](#createmanagedcontrol).  
  
##  <a name="getcontrolhandle"></a>  CWinFormsControl::GetControlHandle  
 Получает дескриптор элемента управления Windows Forms.  
  
```  
inline HWND GetControlHandle() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор для элемента управления Windows Forms.  
  
### <a name="remarks"></a>Примечания  
 `GetControlHandle` — Это вспомогательный метод, который возвращает дескриптор окна, сохраненные в свойствах элементов управления .NET Framework. Значение дескриптора окна копируется [CWnd::m_hWnd](../../mfc/reference/cwnd-class.md#m_hwnd) при вызове [CWnd::Attach](../../mfc/reference/cwnd-class.md#attach).  
  
##  <a name="operator_-_gt"></a>  CWinFormsControl::operator-&gt;  
 Заменяет [CWinFormsControl::GetControl](#getcontrol) в выражениях.  
  
```  
inline TManagedControl^  operator->() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор обеспечивает удобный синтаксис, который заменяет `GetControl` в выражениях.  
  
 Дополнительные сведения о Windows Forms см. в разделе [с помощью пользовательского элемента управления формы Windows в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
##  <a name="operator_tmanagedcontrol"></a>  CWinFormsControl::operator TManagedControl ^  
 Приводит тип как указатель на элемент управления Windows Forms.  
  
```  
inline operator TManagedControl^() const;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот оператор передает `CWinFormsControl<TManagedControl>` для функции, которые принимают указатель на элемент управления Windows Forms.  
  
## <a name="see-also"></a>См. также  
 [Класс CWinFormsDialog](../../mfc/reference/cwinformsdialog-class.md)   
 [Класс CWinFormsView](../../mfc/reference/cwinformsview-class.md)
