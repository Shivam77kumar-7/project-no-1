code :::>

use std::thread;
use std::time::Duration;

fn main() {
    let word = "Tangent";
    let chars: Vec<char> = word.chars().collect();
    let mut frame = 0u32;

    loop {
        // Clear the terminal (ANSI escape)
        print!("\x1b[2J\x1b[H");

        // Build the wave line
        let mut line = String::new();
        for (i, &c) in chars.iter().enumerate() {
            // Sine-wave offset per character
            let offset = ((i as f64 * 0.7 + frame as f64 * 0.3)
                .sin() * 3.0 + 3.0) as usize;
            line.push_str(&" ".repeat(offset));
            line.push(c);
            line.push(' ');
        }

        println!("{}", line);
        std::io::Write::flush(&mut std::io::stdout()).unwrap();

        frame += 1;
        thread::sleep(Duration::from_millis(80));
    }
}
