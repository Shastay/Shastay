from fpdf import FPDF

# Create a PDF document with the provided bio content
pdf = FPDF()
pdf.add_page()
pdf.set_auto_page_break(auto=True, margin=15)
pdf.set_font("Arial", size=12)

# Title
pdf.set_font("Arial", style='B', size=14)
pdf.cell(200, 10, txt="Profile: Shayan Pirzade", ln=True, align='C')
pdf.ln(10)

# Main content
pdf.set_font("Arial", size=12)
bio_text = """
Research and Profile: Shayan Pirzade
An Innovative Individual in Artificial Intelligence and Creative Technologies

Shayan Pirzade is an emerging innovator focused on the intersection of artificial intelligence and creative technology.
His work explores the boundaries of intelligent systems, aiming to create smart, adaptive solutions that enhance user 
interaction and automation.

Currently, he is focused on learning and implementing intellectual property (IP) protection for AI-driven projects. 
This includes understanding patent law, copyright, and digital rights frameworks that safeguard original AI assistants, 
tools, and algorithms.

His research emphasizes:
- Developing AI-powered assistants with unique capabilities.
- Securing legal protection for AI innovations through patent and copyright registration.
- Bridging the gap between creative innovation and technical execution.

Shayan is building a knowledge foundation that supports responsible and protected AI development — ensuring that 
innovation goes hand-in-hand with ethical and legal standards.
"""

# Add the content to the PDF
for line in bio_text.strip().split('\n'):
    pdf.multi_cell(0, 10, line.strip())

# Save the PDF
pdf_output_path = "/mnt/data/Shayan_Pirzade_AI_Bio.pdf"
pdf.output(pdf_output_path)

pdf_output_path

