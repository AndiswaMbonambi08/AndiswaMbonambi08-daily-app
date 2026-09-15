# Shelf

Shelf is a personal reading tracker built for readers who want a simple, visual way to see where every book stands without spreadsheets or sticky notes. It's for me first: someone juggling technical books, novels, and articles at once, who keeps losing track of what's actually still open. In Shelf's Board → Column → Card model, the Board is my whole reading shelf, a Column is a reading stage (Want to Read, Currently Reading, Finished), and a Card is a single book, carrying its title, author, and once finished, my rating and notes.

## Setup
Prerequisites

Flutter SDK (stable channel) installed and on your PATH
A connected device, emulator, or simulator (Android/iOS), or a desktop/web target enabled

## Steps

Clone the repo:
   git clone https://github.com/AndiswaMbonambi08/AndiswaMbonambi08-daily-app.git
   cd AndiswaMbonambi08-daily-app
Install dependencies:
   flutter pub get
Check your setup is ready:
   flutter doctor
Run the app:
   flutter run

## Usage
Add a book: From the board, tap the add button to create a new card in the Want to Read column with a title and author.
Move a book between stages: Drag a card from one column to the next (Want to Read → Currently Reading → Finished) to reflect its actual status.
Rate and review a finished book: Once a card reaches Finished, open it to add a rating and notes.
Find a book: Use search/filter to locate a card by title, author, genre, or stage.
Stay on track: Shelf nudges you if a book has been sitting in Currently Reading for too long.
