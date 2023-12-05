using System;
using System.Drawing;
using System.Windows.Forms;

namespace ColorChangingPanel
{
    public class ColorChangingPanel : Panel
    {
        private Timer timer;
        private Random random;
        private Color borderColor;

        public ColorChangingPanel()
        {
            timer = new Timer();
            random = new Random();

            timer.Interval = 1000; // Set the timer interval to 1 second
            timer.Tick += Timer_Tick; // Attach the event handler for the Tick event
            timer.Start(); // Start the timer
        }

        private void Timer_Tick(object sender, EventArgs e)
        {
            // Generate a random color
            int r = random.Next(256);
            int g = random.Next(256);
            int b = random.Next(256);
            borderColor = Color.FromArgb(r, g, b);

            // Redraw the panel
            this.Invalidate();
        }

        protected override void OnPaint(PaintEventArgs e)
        {
            base.OnPaint(e);
            using (Pen pen = new Pen(borderColor, 3)) // Set the pen width to your desired thickness
            {
                e.Graphics.DrawRectangle(pen, 0, 0, Width - 1, Height - 1);
            }
        }
    }
}
