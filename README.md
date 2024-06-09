Awesome Quotes App
Overview

This Flutter application displays a list of quotes and famous dialogues. The main page shows a list of quotes with their authors. There is a button to navigate to the next page which displays a list of famous dialogues from various movies with their corresponding authors.

Features
List of quotes with authors
List of famous dialogues with authors
Navigation between pages using a FloatingActionButton
Code Structure
Main Entry Point
The entry point of the application is the main function, which initializes and runs the MaterialApp:

dart
Copy code
void main() => runApp(MaterialApp(
  debugShowCheckedModeBanner: false,
  home: QuoteList(),
));
Quote Class
The Quote class represents a quote with a text and an author:

dart
Copy code
class Quote {
  String text;
  String author;

  Quote({required this.text, required this.author});
}
QuoteList Widget
The QuoteList widget is a stateful widget that displays a list of quotes:

dart
Copy code
class QuoteList extends StatefulWidget {
  const QuoteList({super.key});

  @override
  State<QuoteList> createState() => _QuoteListState();
}

class _QuoteListState extends State<QuoteList> {
  List<Quote> quotes = [
    Quote(text: 'Be yourself', author: 'Saroj Karki'),
    Quote(text: 'Who\'s gonna carry the boats?', author: 'David Goggins'),
    Quote(text: 'The truth is rarely pure and never simple', author: 'Oscar Wilde'),
    Quote(text: 'To kyase he ap log', author: 'CarryMinati'),
    Quote(text: 'I am the one only one', author: 'Kendrick Lamar'),
    Quote(text: 'What was I made for', author: 'Billie Eilish'),
    Quote(text: 'Ambani mera lau*e pe', author: 'Technical Guruji'),
    Quote(text: 'The only limit to our realization of tomorrow is our doubts of today.', author: 'Franklin D. Roosevelt'),
    Quote(text: 'Do not watch the clock. Do what it does. Keep going.', author: 'Sam Levenson'),
    Quote(text: 'Keep your face always toward the sunshine—and shadows will fall behind you.', author: 'Walt Whitman'),
    Quote(text: 'It is always the simple that produces the marvelous.', author: 'Amelia Barr'),
    Quote(text: 'The world is full of magical things patiently waiting for our wits to grow sharper.', author: 'Bertrand Russell'),
    Quote(text: 'Let us make our future now, and let us make our dreams tomorrow’s reality.', author: 'Malala Yousafzai'),
  ];

  Widget quoteTemplate(Quote quote) {
    return Card(
      margin: EdgeInsets.fromLTRB(16.0, 16.0, 16.0, 0.0),
      child: Padding(
        padding: const EdgeInsets.all(12.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: <Widget>[
            Text(
              quote.text,
              style: TextStyle(
                fontSize: 18.0,
                color: Colors.grey[600],
              ),
            ),
            SizedBox(height: 6.0),
            Text(
              quote.author,
              style: TextStyle(
                fontSize: 14.0,
                color: Colors.grey[800],
              ),
            ),
          ],
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.grey[200],
      appBar: AppBar(
        title: Text('Awesome Quotes'),
        centerTitle: true,
        backgroundColor: Colors.blueAccent,
      ),
      body: ListView(
        children: quotes.map((quote) => quoteTemplate(quote)).toList(),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: () {
          Navigator.push(
            context,
            MaterialPageRoute(builder: (context) => NextPage()),
          );
        },
        child: Icon(Icons.arrow_forward),
        backgroundColor: Colors.blueGrey,
      ),
    );
  }
}
Dialogue Class
The Dialogue class represents a dialogue with a text and an author:

dart
Copy code
class Dialogue {
  String text;
  String author;

  Dialogue({required this.text, required this.author});
}
NextPage Widget
The NextPage widget is a stateless widget that displays a list of famous dialogues:

dart
Copy code
class NextPage extends StatelessWidget {
  final List<Dialogue> dialogues = [
    Dialogue(text: 'I\'ll be back.', author: 'Terminator'),
    Dialogue(text: 'May the Force be with you.', author: 'Star Wars'),
    Dialogue(text: 'You talking to me?', author: 'Taxi Driver'),
    Dialogue(text: 'Here\'s looking at you, kid.', author: 'Casablanca'),
    Dialogue(text: 'Go ahead, make my day.', author: 'Sudden Impact'),
    Dialogue(text: 'I\'ve got a feeling we\'re not in Kansas anymore.', author: 'The Wizard of Oz'),
    Dialogue(text: 'Houston, we have a problem.', author: 'Apollo 13'),
    Dialogue(text: 'I am your father.', author: 'Star Wars: The Empire Strikes Back'),
    Dialogue(text: 'Elementary, my dear Watson.', author: 'Sherlock Holmes'),
    Dialogue(text: 'I see dead people.', author: 'The Sixth Sense'),
  ];

  Widget dialogueTemplate(Dialogue dialogue) {
    return Card(
      margin: EdgeInsets.fromLTRB(16.0, 16.0, 16.0, 0.0),
      child: Padding(
        padding: const EdgeInsets.all(12.0),
        child: Column(
          crossAxisAlignment: CrossAxisAlignment.stretch,
          children: <Widget>[
            Text(
              dialogue.text,
              style: TextStyle(
                fontSize: 18.0,
                color: Colors.grey[600],
              ),
            ),
            SizedBox(height: 6.0),
            Text(
              dialogue.author,
              style: TextStyle(
                fontSize: 14.0,
                color: Colors.grey[800],
              ),
            ),
          ],
        ),
      ),
    );
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text('Famous Dialogues'),
        centerTitle: true,
        backgroundColor: Colors.blueAccent,
      ),
      body: ListView(
        children: dialogues.map((dialogue) => dialogueTemplate(dialogue)).toList(),
      ),
    );
  }
}
How to Run
Ensure you have Flutter installed on your system. For installation instructions, visit Flutter's official website.
Clone or download this repository.
Open the project in your preferred IDE (e.g., VSCode, Android Studio).
Run flutter pub get to install dependencies.
Connect a device or start an emulator.
Run the app using flutter run.
Future Enhancements
Add functionality to add new quotes and dialogues.
Implement search functionality to find specific quotes or dialogues.
Enhance UI/UX with better styling and animations.
Add user authentication to save favorite quotes and dialogues.
Contributing
Contributions are welcome! Please submit a pull request or open an issue to discuss the changes you want to make.

License
This project is licensed under the MIT License. See the LICENSE file for more details.

Acknowledgements
Flutter for the awesome framework.
Quote and dialogue authors for their inspiring words.
