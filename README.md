- 👋 Hi, I’m @kodcu1234
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
kodcu1234/kodcu1234 is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
import sys
from PyQt5.QtWidgets import *
from PyQt5.QtCore import *
from PyQt5.QtGui import *
from PyQt5.QtWebEngineWidgets import *
from PyQt5.QtPrintSupport import * 


class MainWindow(QMainWindow):
    def __init__(self,*args,**kwargs):
        super(MainWindow,self).__init__(*args,**kwargs)

        #tarayıcımızın ismini belirliyoruz
        self.setWindowTitle("Kerberos Web Browser") 

        #tarayıcının iconunu belirliyoruz
        self.setWindowIcon(QIcon("logo.png"))

        #Çalışırken tam ekran olmasını ve minimum genişlik-yüksekliğini belirliyoruz
        self.setMinimumSize(500,500)
        self.showMaximized()

        #QtWebEngineWidgets modulünden tarayıcımızın temelini oluşturcak fonksiyonu çağırıyoruz
        self.browser = QWebEngineView()

        #başlangıçtaki sayfamızı belirliyoruz, burayı istediğiniz herhangi bir sitenin linki yapabilirsiniz
        self.browser.setUrl(QUrl("http://www.google.com"))

        #uygulamamızı qt arayüzümüze yerleştiriyoruz
        self.setCentralWidget(self.browser)



#class yapımızın çalışması için gerekli fonksiyonlar
app = QApplication(sys.argv)
main=MainWindow()
main.show()
sys.exit(app.exec_())

