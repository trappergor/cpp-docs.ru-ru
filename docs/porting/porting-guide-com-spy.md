---
title: 'Руководство по переносу: COM Spy'
ms.date: 11/04/2016
ms.assetid: 24aa0d52-4014-4acb-8052-f4e2e4bbc3bb
ms.openlocfilehash: ca81b240a102195109c0ad6ef05bfaed10306704
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57751691"
---
# <a name="porting-guide-com-spy"></a>Руководство по переносу: COM Spy

Это второй раздел в серии статей, в которых описывается процесс обновления старых проектов Visual C++ до последней версии среды Visual Studio. Пример кода в этом разделе был в последний раз скомпилирован с помощью Visual Studio 2005.

## <a name="comspy"></a>COMSpy

COMSpy — это программа, которая отслеживает и регистрирует действия обслуживаемых компонентов на компьютере. Обслуживаемыми компонентами являются компоненты COM+, которые выполняются в системе и могут использоваться компьютерами в одной и той же сети. Для их управления используются функциональные возможности служб компонентов на панели управления Windows.

### <a name="step-1-converting-the-project-file"></a>Шаг 1. Преобразование файла проекта.
Файл проекта легко преобразуется и создает отчет о миграции. Отчет содержит несколько записей, которые позволяют узнать о наличии возможных проблем. В отчете указывается одна проблема (обратите внимание, что в этом разделе сообщения об ошибках иногда сокращаются для удобства чтения, например удаляются полные пути):

```Output
ComSpyAudit\ComSpyAudit.vcproj: MSB8012: $(TargetPath) ('C:\Users\UserName\Desktop\spy\spy\ComSpyAudit\.\XP32_DEBUG\ComSpyAudit.dll') does not match the Librarian's OutputFile property value '.\XP32_DEBUG\ComSpyAudit.dll' ('C:\Users\UserName\Desktop\spy\spy\XP32_DEBUG\ComSpyAudit.dll') in project configuration 'Unicode Debug|Win32'. This may cause your project to build incorrectly. To correct this, please make sure that $(TargetPath) property value matches the value specified in %(Lib.OutputFile).
```

Одна из часто встречающихся проблем при обновлении проектов заключается в том, что может потребоваться проверка параметра **OutputFile компоновщика** в диалоговом окне "Свойства проекта". Для проектов, созданных до появления Visual Studio 2010, OutputFile, — это тот параметр, с которым у мастера автоматического преобразования возникают проблемы, если для данного параметра установлено нестандартное значение. В этом случае пути для выходных файлов должны указывать на нестандартную папку XP32_DEBUG. Чтобы узнать больше об этой ошибке, мы ознакомились с [публикацией в блоге](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx), которая относится к обновлению проектов Visual C++ 2010, а именно к переходу с vcbuild на msbuild, что является существенным изменением. В соответствии с этой информацией значением по умолчанию для параметра **Выходной файл** при создании нового проекта является `$(OutDir)$(TargetName)$(TargetExt)`, но оно не задается во время преобразования, так как преобразованные проекты не в состоянии проверить, что все работает правильно. Тем не менее давайте попробуем ввести это значение для параметра OutputFile и проверить его работоспособность.  Все в порядке, поэтому можно продолжать. Если нет конкретной причины для использования нестандартной выходной папки, рекомендуется использовать стандартное расположение. В этом случае мы сохраняем нестандартное расположение для выходных файлов во время процесса переноса и обновления; `$(OutDir)` разрешается в папку XP32_DEBUG в конфигурации **отладки** и в папку ReleaseU для конфигурации **выпуска**.

### <a name="step-2-getting-it-to-build"></a>Шаг 2. Выполнение сборки до достижения успеха
При сборке перенесенного проекта выводится несколько сообщений об ошибках и предупреждений.

При этом `ComSpyCtl` не выполняет компиляцию из-за этой ошибки компилятора:

```Output
atlcom.h(611): error C2664: 'HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM,BOOL,ATL::ATL_PROPMAP_ENTRY *)': cannot convert argument 3 from 'const ATL::ATL_PROPMAP_ENTRY *' to 'ATL::ATL_PROPMAP_ENTRY *'atlcom.h(611): note: Conversion loses qualifiersatlcom.h(608): note: while compiling class template member function 'HRESULT ATL::IPersistStreamInitImpl<CComSpy>::Save(LPSTREAM,BOOL)'\spy\spy\comspyctl\ccomspy.h(28): note: see reference to class template instantiation 'ATL::IPersistStreamInitImpl<CComSpy>' being compiled
```

Ошибка ссылается на метод `Save` в классе `IPersistStreamInitImpl` в файле atlcom.h.

```cpp
STDMETHOD(Save)(_Inout_ LPSTREAM pStm, _In_ BOOL fClearDirty)
{
     T* pT = static_cast<T*>(this);
     ATLTRACE(atlTraceCOM, 2, _T("IPersistStreamInitImpl::Save\n"));
     return pT->IPersistStreamInit_Save(pStm, fClearDirty, T::GetPropertyMap());
}
```

Проблема заключается в том, что преобразование, которое выполняет более старая версия компилятора, больше не является допустимым. Для соответствия стандарту C++ некоторый код, который ранее был разрешен, теперь не разрешается. В этом случае небезопасно передавать указатель, отличный от const, в функцию, ожидающую указатель const.  Решение заключается в поиске объявления метода `IPersistStreamInit_Save` в классе `CComSpy` и добавлении модификатора const в третий параметр.

```cpp
HRESULT CComSpy::IPersistStreamInit_Save(LPSTREAM pStm, BOOL /* fClearDirty */, const ATL_PROPMAP_ENTRY* pMap)
```

И аналогичном изменении для `IPersistStreamInit_Load`.

```cpp
HRESULT IPersistStreamInit_Load(LPSTREAM pStm, const ATL_PROPMAP_ENTRY* pMap);
```

Следующая ошибка относится к регистрации.

```Output
error MSB3073: The command "regsvr32 /s /c "C:\Users\username\Desktop\spy\spy\ComSpyCtl\.\XP32_DEBUG\ComSpyCtl.lib"error MSB3073: echo regsvr32 exec. time > ".\XP32_DEBUG\regsvr32.trg"error MSB3073:error MSB3073: :VCEnd" exited with code 3.
```

Эта команда регистрации после сборки нам больше не нужна. Вместо этого мы просто удаляем настраиваемую команду сборки и указываем в параметрах **компоновщика**, что необходимо регистрировать выходные данные.

### <a name="dealing-with-warnings"></a>Работа с предупреждениями
Проект создает следующее предупреждение компоновщика.

```Output
warning LNK4075: ignoring '/EDITANDCONTINUE' due to '/SAFESEH' specification
```

Параметр компилятора `/SAFESEH` в режиме отладки не используется (данный режим задействуется в случае применения `/EDITANDCONTINUE`), поэтому для устранения проблемы параметр `/SAFESEH` следует отключать только для конфигураций **отладки**. Для этого следует открыть диалоговое окно свойств для проекта, который создает эту ошибку, для **конфигурации** установить значение **Отладка** (фактически **Отладка Юникода**), а в разделе **Компоновщик | Дополнительно** сбросить свойство **Образ имеет безопасных обработчиков исключений** в значение **Нет** (`/SAFESEH:NO`).

Компилятор предупреждает, что `PROP_ENTRY_EX` является устаревшим. Он не является безопасным, его рекомендуется заменить на `PROP_ENTRY_TYPE_EX`.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_ENTRY_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Мы изменяем код в файле ccomspy.h соответствующим образом и при необходимости добавляем типы COM.

```cpp
BEGIN_PROPERTY_MAP(CComSpy)
     PROP_ENTRY_TYPE_EX( "LogFile", DISPID_LOGFILE, CLSID_ComSpyPropPage, IID_IComSpy, VT_BSTR)
     PROP_ENTRY_TYPE_EX( "ShowGridLines", DISPID_GRIDLINES, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "Audit", DISPID_AUDIT, CLSID_ComSpyPropPage, IID_IComSpy, VT_BOOL)
     PROP_ENTRY_TYPE_EX( "ColWidth", DISPID_COLWIDTH, CLSID_ComSpyPropPage, IID_IComSpy, VT_UINT)
     PROP_PAGE(CLSID_StockFontPage)
END_PROPERTY_MAP()
```

Мы добрались до нескольких последних предупреждений, которые также вызываются более строгими проверками на соответствие стандартам компилятора:

```Output
\spy\comspyctl\usersub.h(70): warning C4457: declaration of 'var' hides function parameter\spy\comspyctl\usersub.h(48): note: see declaration of 'var'\spy\comspyctl\usersub.h(94): warning C4018: '<': signed/unsigned mismatch  ComSpy.cpp\spy\comspyctl\comspy.cpp(186): warning C4457: declaration of 'bHandled' hides function parameter\spy\spy\comspyctl\comspy.cpp(177): note: see declaration of 'bHandled'
```

Из этого кода поступает предупреждение C4018:

```cpp
for (i=0;i<lCount;i++)
    CoTaskMemFree(pKeys[i]);
```

Проблема состоит в том, что `i` объявляется как `UINT`, а `lCount` объявляется как **long**, поэтому имеется несоответствие типов со знаком или без знака. Менять тип `lCount` на `UINT` будет неудобно, так как он получает свое значение из метода `IMtsEventInfo::get_Count`, использующего тип **long**, и не находится в коде пользователя. Поэтому мы добавим приведение в код. Приведение типов в стиле C подойдет для данного числового приведения, но рекомендуется использовать стиль **static_cast**.

```cpp
for (i=0;i<static_cast<UINT>(lCount);i++)
    CoTaskMemFree(pKeys[i]);
```

Эти предупреждения появляются в случаях, когда переменная была объявлена в функции, которая имеет параметр с тем же именем, что может запутать код. Для устранения этой проблемы мы изменяем имена локальных переменных.

### <a name="step-3-testing-and-debugging"></a>Шаг 3. Тестирование и отладка
Сначала мы протестировали приложение путем запуска различных меню и команд, а затем закрыли приложение. Единственной обнаруженной проблемой было утверждение отладки после закрытия приложения. Проблема появлялась в деструкторе для `CWindowImpl` (базовом классе объекта `CSpyCon`), который является основным COM-компонентом приложения. В следующем коде в atlwin.h произошел сбой утверждения.

```cpp
virtual ~CWindowImplRoot()
{
     #ifdef _DEBUG
     if(m_hWnd != NULL)// should be cleared in WindowProc
     {
          ATLTRACE(atlTraceWindowing, 0, _T("ERROR - Object deleted before window was destroyed\n"));
          ATLASSERT(FALSE);
     }
     #endif //_DEBUG
}
```

`hWnd` обычно устанавливается в нуль в функции `WindowProc`, однако этого не произошло, так как вместо `WindowProc` по умолчанию вызывается настраиваемый обработчик для сообщения Windows (WM_SYSCOMMAND), который закрывает окно. Настраиваемый обработчик не устанавливал `hWnd` в нуль. Если взглянуть на похожий код в классе `CWnd` в MFC, будет видно, что при уничтожении окна вызывается `OnNcDestroy`, а в MFC документация рекомендует сделать следующее: при переопределении `CWnd::OnNcDestroy` должен быть вызван базовый `NcDestroy`, чтобы убедиться в том, что выполняются правильные операции очистки, включая отделение дескриптора окна от окна (другими словами, `hWnd` устанавливается в нуль). Это утверждение также может запускаться в исходной версии примера, поскольку в старой версии atlwin.h присутствовал тот же код утверждения.

Для тестирования функциональных возможностей приложения мы создали **обслуживаемый компонент** с помощью шаблона проекта ATL и добавили поддержку COM+ в мастере проектов ATL. Даже если раньше вы не работали с обслуживаемыми компонентами, будет несложно создать и зарегистрировать такой компонент, а затем сделать его доступным в системе или в сети для других приложений. Приложение COM Spy предназначено для отслеживания активности обслуживаемых компонентов в качестве средства диагностики.

Затем мы добавили класс, выбрали объект ATL и присвоили ему имя `Dog`. Затем в файлах dog.h и dog.cpp добавили реализацию.

```cpp
STDMETHODIMP CDog::Wag(LONG* lDuration)
{
    // TODO: Add your implementation code here
    *lDuration = 100l;
    return S_OK;
}
```

Затем построили и зарегистрировали ее (необходимо запустить Visual Studio от имени администратора), а затем мы активировали ее с помощью приложения с **обслуживаемым компонентом** на панели управления Windows. Мы создали проект Windows Forms в C#, перетащили кнопку в форму с панели элементов и дважды щелкнули ее для перехода к обработчику событий щелчка кнопкой мыши. Чтобы создать экземпляр компонента `Dog`, мы добавили следующий код.

```cpp
private void button1_Click(object sender, EventArgs e)
{
    ATLProjectLib.Dog dog1 = new ATLProjectLib.Dog();
    dog1.Wag();
}
```

Все это работает без проблем. При включенном приложении COM Spy, которое функционирует и настроено для отслеживания компонента `Dog`, поступает большой объем данных, указывающих на выполняемые действия.

## <a name="see-also"></a>См. также

[Перенос и обновление: примеры и конкретные случаи](../porting/porting-and-upgrading-examples-and-case-studies.md)<br/>
[Следующий пример: Spy++](../porting/porting-guide-spy-increment.md)<br/>
[Предыдущий пример: MFC Scribble](../porting/porting-guide-mfc-scribble.md)
