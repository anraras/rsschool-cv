Oleh Poslusniy


Contacts


Phone: +38 063 7724639
E-mail: oleg.fort27@gmail.com
Telegram: @oleg_poslushnoy


About me


I worked at a factory that makes rockets, but became interested in programming. 
Now I am a freelancer to earn money and I study in my free time. I really want to learn new professions


Skills


HTML, CSS
Python, Flask
Git
Typing
Translate
Adobe Photoshop, Adobe Reader


Code example:


Mini game with number in Flask
import config
from flask_wtf import FlaskForm
from flask import Flask, request, url_for
import random
from wtforms import IntegerField, validators
class Riddler(object): #class for riddler  numbers
	number = None
	@classmethod
	def new_number(cls, max):
		cls.number = random.randint(1, max)
		print('Riddler number is ', cls.number)
class GuessForm(FlaskForm):
	number = IntegerField(label='Nuber is ', validators=[validators.Required()])
app = Flask(__name__)
app.config.from_object(config)
@app.route('/', methods=['GET'])
def home():
	Riddler.new_number(100)
	print(Riddler.number)
	return ' Number is  riddler'
@app.route('/guess', methods=['POST'])
def guess():
	if Riddler.number == None:
		return '<a href="/">Вы не загадали число</a>'
	form=GuessForm(request.form)
	if form.validate():
		user_number = form.number.data
		if user_number == Riddler.number:
			Riddler.new_number(100)
			return 'You win!!! another number is  riddler'
		elif user_number < Riddler.number:
			return ' > '
		elif user_number > Riddler.number:
			return '<'
	else:
		return str(form.errors)
if __name__=='__main__':
	app.run()


Education:


State University of Telecommunications, College of radio electronics


Languages:


English - B1
Ukrainian - Native
Russian - Native
Polish - B1
