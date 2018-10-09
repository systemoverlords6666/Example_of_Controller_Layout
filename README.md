// Example_of_Controller_Layout

//The Wheels Part

import com.qualcomm.robotcore.eventloop.opmode.OpMode;
import com.qualcomm.robotcore.eventloop.opmode.TeleOp;
import com.qualcomm.robotcore.hardware.DcMotor;

@TeleOp(name = "TeleOP_wheels")
public class TeleOP_6666_wheels extends OpMode{

    DcMotor lm;
    DcMotor rm;
    double leftwheelpower;
    double rightwheelpower;


    @Override
    public void init() {

        lm = hardwareMap.dcMotor.get("lm");
        rm = hardwareMap.dcMotor.get("rm");


        rm.setDirection(DcMotor.Direction.REVERSE);
    }

    @Override
    public void loop() {

        leftwheelpower = gamepad1.left_stick_y;
        rightwheelpower = gamepad1.right_stick_y;

        lm.setPower(leftwheelpower);
        rm.setPower(rightwheelpower);

    }
}
