#  pip install -U wxPython
 istall wx

# создание класса MyFrame
class MyFrame(wx.Frame):
    # Функция инициализации класса
    def __init__(self):
        # Заголовок окна
        wx.Frame.__init__(self, None, title="УСПЕШНО!", size=(420, 170),
                          style=wx.DEFAULT_FRAME_STYLE ^ wx.RESIZE_BORDER)
        # создание панели
        panel = wx.Panel(self)
        # Изменение размера шрифта
        font = wx.SystemSettings.GetFont(wx.SYS_DEFAULT_GUI_FONT)
        font.SetPointSize(10)
        panel.SetFont(font)
        # Создание диалогового окна с прогресс баром
        pulse_dlg = wx.ProgressDialog(title="Загрузка вируса", message="Установка...", maximum=100)
        # Цикл, в котором мы заставляем двигаться наш прогресс бар
        for i in range(100):
            wx.MilliSleep(25)
            pulse_dlg.Update(1 * i)
        # Создание сайзера, текста и кнопки
        main_sizer = wx.BoxSizer(wx.VERTICAL)
        txt = wx.StaticText(panel, label='Вирус успешно установлен!')
        but = wx.Button(panel, label='Блин!')
        main_sizer.Add(txt, flag=wx.ALIGN_CENTER | wx.TOP | wx.BOTTOM, border=30)
        main_sizer.Add(but, flag=wx.ALIGN_CENTER | wx.BOTTOM, border=20)
        # Сайзер на панель
        panel.SetSizer(main_sizer)
        # вызов функции при нажатии на кнопку
        self.Bind(wx.EVT_BUTTON, self.Nice)

    # функция
    def Nice(self, event):
        frame.Destroy()


app = wx.App()
frame = MyFrame()
frame.Show()
app.MainLoop()
